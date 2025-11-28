# API Reference

This document describes the internal JavaScript API of Silence of the Lags for developers who want to customize or extend the application.

## SpeedTest Class

The main class that handles all speed testing functionality.

### Constructor

```javascript
const speedTest = new SpeedTest();
```

Creates a new SpeedTest instance.

### Static Methods

#### `SpeedTest.isOnline()`

Check if the device is online.

```javascript
if (SpeedTest.isOnline()) {
    // Device is online
}
```

**Returns:** `boolean`

#### `SpeedTest.getConnectionInfo()`

Get information about the current connection (if available).

```javascript
const info = SpeedTest.getConnectionInfo();
// Returns: { type: 'wifi', downlink: 10, rtt: 50 }
// Or null if not available
```

**Returns:** `Object | null`
- `type`: Connection type ('wifi', '4g', '3g', etc.)
- `downlink`: Estimated downlink speed in Mbps
- `rtt`: Round-trip time in ms

### Instance Methods

#### `run(callbacks)`

Start the full speed test.

```javascript
const result = await speedTest.run({
    onPhase: (phase) => console.log('Phase:', phase),
    onPingComplete: (ping, jitter, loss) => {},
    onDownloadProgress: (speed, progress) => {},
    onDownloadComplete: (speed) => {},
    onUploadProgress: (speed, progress) => {},
    onUploadComplete: (speed) => {}
});
```

**Parameters:**
- `callbacks.onPhase(phase)`: Called when test phase changes ('ping', 'download', 'upload')
- `callbacks.onPingComplete(ping, jitter, loss)`: Called when ping test completes
- `callbacks.onDownloadProgress(speedMbps, progress)`: Called during download (progress 0-1)
- `callbacks.onDownloadComplete(speedMbps)`: Called when download completes
- `callbacks.onUploadProgress(speedMbps, progress)`: Called during upload (progress 0-1)
- `callbacks.onUploadComplete(speedMbps)`: Called when upload completes

**Returns:** `Promise<Object>` with results:
```javascript
{
    ping: 25,        // Median ping in ms
    jitter: 3.5,     // Jitter in ms
    packetLoss: 0,   // Packet loss percentage
    download: 156.5, // Download speed in Mbps
    upload: 45.2     // Upload speed in Mbps
}
```

#### `stop()`

Stop the current test.

```javascript
speedTest.stop();
```

#### `measurePing()`

Measure ping/latency only.

```javascript
const ping = await speedTest.measurePing();
console.log('Ping:', ping, 'ms');
console.log('Jitter:', speedTest.results.jitter, 'ms');
console.log('Packet Loss:', speedTest.results.packetLoss, '%');
```

**Returns:** `Promise<number | null>`

#### `measureDownload(onProgress)`

Measure download speed only.

```javascript
const speed = await speedTest.measureDownload((speedMbps, progress) => {
    console.log('Speed:', speedMbps, 'Progress:', progress * 100, '%');
});
console.log('Final:', speed, 'Mbps');
```

**Returns:** `Promise<number | null>`

#### `measureUpload(onProgress)`

Measure upload speed only.

```javascript
const speed = await speedTest.measureUpload((speedMbps, progress) => {
    console.log('Speed:', speedMbps, 'Progress:', progress * 100, '%');
});
console.log('Final:', speed, 'Mbps');
```

**Returns:** `Promise<number | null>`

## Utils Object

Utility functions used throughout the application.

### `Utils.now()`

Get high-precision timestamp.

```javascript
const start = Utils.now();
// ... do something ...
const elapsed = Utils.now() - start;
```

**Returns:** `number` (milliseconds)

### `Utils.formatBytes(bytes)`

Format bytes to human-readable string.

```javascript
Utils.formatBytes(1536); // "1.5 KB"
Utils.formatBytes(1048576); // "1 MB"
```

**Returns:** `string`

### `Utils.formatTime(seconds)`

Format seconds to human-readable duration.

```javascript
Utils.formatTime(45); // "45.0 sec"
Utils.formatTime(125); // "2m 5s"
Utils.formatTime(3725); // "1h 2m"
```

**Returns:** `string`

### `Utils.median(array)`

Calculate median of an array.

```javascript
Utils.median([1, 2, 3, 4, 5]); // 3
```

**Returns:** `number`

### `Utils.stdDev(array)`

Calculate standard deviation.

```javascript
Utils.stdDev([1, 2, 3, 4, 5]); // ~1.414
```

**Returns:** `number`

### `Utils.debounce(func, wait)`

Create debounced function.

```javascript
const debouncedResize = Utils.debounce(() => {
    console.log('Resized');
}, 150);

window.addEventListener('resize', debouncedResize);
```

**Returns:** `function`

## CONFIG Object

Configuration constants.

```javascript
const CONFIG = {
    downloadUrls: [...],         // Array of CDN URLs for download tests
    useFallback: true,           // Use fallback if tests fail
    downloadTestDuration: 8000,  // Download test duration (ms)
    uploadTestDuration: 6000,    // Upload test duration (ms)
    pingCount: 10,               // Number of ping samples
    minChunkSize: 10240,         // Minimum chunk size for measurements
    usePerformanceAPI: true      // Use Performance API for timing
};
```

## UI Object

UI controller for updating the interface.

### Methods

- `UI.updateSpeed(speedMbps)` - Update main speed display
- `UI.updateProgress(percent)` - Update progress bar (0-1)
- `UI.updateStatus(text, color)` - Update status text
- `UI.updateStats(ping, jitter, loss)` - Update stats cards
- `UI.calculateEstimates(speedMbps)` - Show download time estimates
- `UI.showResults(download, upload)` - Show final results
- `UI.updateConnectionStatus()` - Update connection indicator
- `UI.reset()` - Reset all UI elements
- `UI.showHome()` - Show home page
- `UI.showWorking()` - Show working page
- `UI.showComplete()` - Show completion state

## Events

### Connection Events

```javascript
window.addEventListener('online', () => {
    console.log('Back online');
});

window.addEventListener('offline', () => {
    console.log('Gone offline');
});
```

### Visibility Events

The application automatically pauses animations when the page is hidden:

```javascript
document.addEventListener('visibilitychange', () => {
    if (document.hidden) {
        // Page is hidden, animations paused
    } else {
        // Page is visible, animations resumed
    }
});
```

## Customization Examples

### Custom Test Duration

```javascript
// Modify config before running test
CONFIG.downloadTestDuration = 15000; // 15 seconds
CONFIG.uploadTestDuration = 10000;   // 10 seconds
```

### Custom Progress Handler

```javascript
const speedTest = new SpeedTest();
await speedTest.run({
    onDownloadProgress: (speed, progress) => {
        // Custom visualization
        myCustomGauge.setValue(speed);
        myProgressBar.setProgress(progress * 100);
    }
});
```

### Ping-Only Test

```javascript
const speedTest = new SpeedTest();
speedTest.isRunning = true;
speedTest.abortController = new AbortController();

const ping = await speedTest.measurePing();
console.log('Ping:', ping, 'ms');
console.log('Jitter:', speedTest.results.jitter, 'ms');
```
