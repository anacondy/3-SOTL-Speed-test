# How Speed Testing Works

This document explains the technical details of how Silence of the Lags measures your internet speed.

## Overview

Internet speed testing involves measuring how quickly data can be transferred between your device and remote servers. Our application uses modern web technologies to provide accurate measurements.

## Test Phases

### 1. Ping/Latency Test

**What it measures:** Round-trip time for small data packets

**How it works:**
1. The application sends 10 small HTTP HEAD requests to CDN servers
2. Each request measures the time from send to response
3. The median value is used as the final ping result
4. Jitter is calculated as the standard deviation of all ping measurements

**What the results mean:**
- **< 20ms**: Excellent - ideal for gaming and video calls
- **20-50ms**: Good - suitable for most activities
- **50-100ms**: Fair - may notice slight delays
- **> 100ms**: Poor - noticeable lag in real-time applications

### 2. Download Speed Test

**What it measures:** How fast data can be downloaded to your device

**How it works:**
1. Multiple files are downloaded simultaneously from CDN servers
2. The application uses the Fetch API with streaming readers
3. Speed is calculated by measuring bytes received over time
4. Updates are provided every 200ms for real-time display
5. The 90th percentile of measurements is used for final result

**Technical details:**
- Uses `ReadableStream` for accurate byte counting
- Cache-busting ensures fresh downloads each test
- Parallel downloads saturate your connection

**What the results mean:**
| Speed | Use Cases |
|-------|-----------|
| 1-5 Mbps | Basic web browsing, email |
| 5-25 Mbps | SD video streaming, gaming |
| 25-100 Mbps | HD video streaming, large downloads |
| 100-500 Mbps | 4K streaming, fast downloads |
| 500+ Mbps | Professional use, multiple users |

### 3. Upload Speed Test

**What it measures:** How fast data can be sent from your device

**How it works:**
1. Test data blobs are generated locally
2. Upload speed is estimated based on connection type
3. Multiple samples are taken over the test duration
4. Median value provides the final result

**Note:** Browser-based upload testing has limitations due to cross-origin restrictions. Desktop applications provide more accurate upload measurements.

### 4. Packet Loss

**What it measures:** Percentage of data packets that fail to reach their destination

**How it works:**
1. Failed ping requests are counted
2. Packet loss = (failed requests / total requests) × 100

**What the results mean:**
- **0%**: Perfect connection
- **0-1%**: Excellent - minor issues possible
- **1-5%**: Fair - may affect real-time applications
- **> 5%**: Poor - significant connection issues

## Accuracy Considerations

### Factors Affecting Accuracy

1. **Network Congestion**: High traffic times may show lower speeds
2. **Server Distance**: Test servers are geographically distributed via CDN
3. **WiFi vs Ethernet**: Wired connections provide more stable results
4. **Background Applications**: Other apps using bandwidth affect results
5. **VPN Usage**: VPNs add overhead and may limit speeds
6. **Browser Limitations**: Native apps can access more accurate APIs

### Improving Accuracy

1. Run tests at different times of day
2. Use wired Ethernet when possible
3. Close unnecessary applications
4. Disable VPN during testing
5. Run multiple tests and compare

## Technical Implementation

### APIs Used
- **Fetch API**: For downloading test files
- **Performance API**: High-precision timing
- **Network Information API**: Connection type detection (when available)
- **ReadableStream**: For byte-level download tracking

### CDN Endpoints
We use public CDN endpoints for reliable, globally-distributed test servers:
- jQuery CDN
- Bootstrap CDN
- Lodash CDN

### Browser Compatibility
- All modern browsers (Chrome, Firefox, Safari, Edge)
- Graceful fallback for older browsers
- No plugins or extensions required
