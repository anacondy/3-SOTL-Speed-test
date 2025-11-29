# Troubleshooting

Having issues with Silence of the Lags? This guide covers common problems and solutions.

## Connection Issues

### "Offline" Status Shown

**Symptoms:** The connection indicator shows red/offline even when connected.

**Solutions:**
1. Check your internet connection
2. Refresh the page
3. Check if other websites work
4. Disable browser extensions that might block requests
5. Try a different browser

### Test Won't Start

**Symptoms:** Clicking "Initiate Test" does nothing.

**Solutions:**
1. Check if JavaScript is enabled
2. Disable ad blockers temporarily
3. Clear browser cache and cookies
4. Try incognito/private mode
5. Update your browser

## Speed Test Issues

### Very Low Speed Results

**Symptoms:** Results are much lower than expected.

**Possible causes:**
1. **Network congestion**: Test at different times
2. **Background downloads**: Close other apps
3. **VPN enabled**: Disable VPN during test
4. **WiFi interference**: Move closer to router
5. **ISP throttling**: Test with different servers

### Test Freezes or Stalls

**Symptoms:** Progress bar stops moving.

**Solutions:**
1. Wait a few seconds; some phases take longer
2. Refresh the page and try again
3. Check your connection stability
4. Try from a different device

### Inconsistent Results

**Symptoms:** Results vary significantly between tests.

**This is normal if:**
- Testing at different times of day
- Using WiFi (more variable than Ethernet)
- Other devices are using the network

**Try these for consistent results:**
1. Use wired Ethernet connection
2. Test when network is idle
3. Run multiple tests and average

## Display Issues

### UI Doesn't Look Right

**Symptoms:** Layout broken, text overlapping, etc.

**Solutions:**
1. Try zooming to 100% (Ctrl/Cmd + 0)
2. Clear browser cache
3. Disable browser extensions
4. Update your browser
5. Try a different browser

### Animations Are Choppy

**Symptoms:** Background visualizer stutters.

**Solutions:**
1. Close other browser tabs
2. Enable hardware acceleration in browser settings
3. Update graphics drivers
4. If issues persist, the app respects `prefers-reduced-motion`

### Screen Too Dark/Can't Read Text

**Solutions:**
1. Increase screen brightness
2. Disable dark mode browser extensions
3. Check monitor/display settings

## Desktop App Issues

### App Won't Install (Windows)

**Solutions:**
1. Run installer as Administrator
2. Check Windows Defender/antivirus isn't blocking
3. Ensure you have 100MB free space
4. Download a fresh copy of the installer

### App Won't Open (macOS)

**Solutions:**
1. Right-click > Open (to bypass Gatekeeper)
2. Go to System Preferences > Security & Privacy > Allow
3. Check Console.app for error messages

### App Crashes on Start (Linux)

**Solutions:**
1. Install missing dependencies: `sudo apt install libgtk-3-0`
2. Run from terminal to see error messages
3. Try the deb package instead of AppImage

## Mobile App Issues

### App Won't Install (Android)

**Solutions:**
1. Enable "Install from Unknown Sources"
2. Check storage space (need 50MB)
3. Uninstall previous version first
4. Download APK again (may be corrupted)

### High Battery Usage

**The app may use more battery when:**
- Running speed tests (network radio active)
- Animations are playing

**To reduce battery usage:**
1. Enable "Reduce Motion" in system settings
2. Close app when not in use
3. Test while charging if concerned

## Getting More Help

If these solutions don't work:

1. **Check GitHub Issues**: [Search existing issues](https://github.com/anacondy/3-SOTL-Speed-test/issues)
2. **Open New Issue**: Include:
   - Device/OS version
   - Browser/app version
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if applicable

## Reporting Bugs

When reporting bugs, please include:

```
Device: [e.g., iPhone 13, Samsung Galaxy S21, MacBook Pro]
OS: [e.g., iOS 16.1, Android 13, macOS 13.0]
Browser/App Version: [e.g., Chrome 119, Desktop App 2.1.0]
Issue: [Clear description]
Steps to Reproduce:
1. 
2. 
3. 
Expected Behavior: 
Actual Behavior: 
```
