# Silence of the Lags - Speed Test

[![Deploy to GitHub Pages](https://github.com/anacondy/3-SOTL-Speed-test/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/anacondy/3-SOTL-Speed-test/actions/workflows/deploy-pages.yml)
[![Build Cross-Platform Apps](https://github.com/anacondy/3-SOTL-Speed-test/actions/workflows/build-apps.yml/badge.svg)](https://github.com/anacondy/3-SOTL-Speed-test/actions/workflows/build-apps.yml)

## 🌐 Live Demo

**[➡️ Launch Speed Test](https://anacondy.github.io/3-SOTL-Speed-test/)**

---

## 📖 Overview

**Silence of the Lags** is a minimal, elegant, and highly accurate internet speed test application. It measures your download speed, upload speed, ping, jitter, and packet loss with real-time visualizations.

### ✨ Features

- **Real-Time Speed Measurement** - Accurate download and upload speed testing
- **Ping & Jitter Analysis** - Measure network latency and stability
- **Packet Loss Detection** - Identify network reliability issues
- **Cross-Platform** - Works on any device with a modern web browser
- **Responsive Design** - Optimized for all screen sizes and aspect ratios
- **Offline Detection** - Automatically detects connection status
- **Privacy First** - No data stored, all tests run locally
- **Native Apps** - Available for Android, iOS, Windows, macOS, and Linux

---

## 📸 Screenshots

### Desktop View
![Desktop Home Screen](https://github.com/user-attachments/assets/569c8ddc-3d40-4db3-b10a-69ad0c376d27)

*Home screen with elegant dark theme and connection status indicator*

### Speed Test Results
![Speed Test Results](https://github.com/user-attachments/assets/32ddba94-b943-41ab-bd3c-728b84bc9a6c)

*Test results showing download/upload speeds, ping, jitter, and packet loss*

### Mobile View
![Mobile View](https://github.com/user-attachments/assets/8730f93a-c9bf-4122-8f95-ad20776e604f)

*Fully responsive design optimized for mobile devices*

### Ultra-Wide Display
![Ultra-Wide View](https://github.com/user-attachments/assets/41c4f53a-fd4c-41af-b4a0-e0125dc33ccb)

*Optimized layout for ultra-wide monitors (21:9 and wider)*

---

## 📱 Download Apps

### Supported Platforms

| Platform | Download | Min Requirements |
|----------|----------|------------------|
| **Android** | [Download APK](https://github.com/anacondy/3-SOTL-Speed-test/releases/latest) | Android 7.0+ (API 24), 50MB storage |
| **iOS** | Coming Soon | iOS 13.0+, 50MB storage |
| **Windows** | [Download EXE](https://github.com/anacondy/3-SOTL-Speed-test/releases/latest) | Windows 10+, 100MB storage |
| **macOS** | [Download DMG](https://github.com/anacondy/3-SOTL-Speed-test/releases/latest) | macOS 10.15+, 100MB storage |
| **Linux** | [Download AppImage](https://github.com/anacondy/3-SOTL-Speed-test/releases/latest) | Ubuntu 18.04+/Debian 10+, 100MB storage |

---

## 💻 System Requirements

### Web Browser (Recommended)
- **Chrome** 80+
- **Firefox** 75+
- **Safari** 13+
- **Edge** 80+
- **Opera** 67+

### Desktop Application
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **OS** | Windows 10 / macOS 10.15 / Ubuntu 18.04 | Latest version |
| **RAM** | 512 MB | 1 GB |
| **Storage** | 100 MB | 200 MB |
| **Display** | 320x480 | 1920x1080+ |
| **Network** | Any internet connection | Broadband 10+ Mbps |

### Mobile Application
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **Android** | 7.0 (Nougat) | 11+ |
| **iOS** | 13.0 | 15+ |
| **RAM** | 1 GB | 2 GB |
| **Storage** | 50 MB | 100 MB |

---

## 🚀 Getting Started

### Use Online
Simply visit the [live demo](https://anacondy.github.io/3-SOTL-Speed-test/) in any modern web browser.

### Run Locally
```bash
# Clone the repository
git clone https://github.com/anacondy/3-SOTL-Speed-test.git

# Open in browser
cd 3-SOTL-Speed-test
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux
```

### Build Desktop App
```bash
# Install dependencies
cd electron-app
npm install

# Run in development
npm start

# Build for current platform
npm run build
```

---

## 📊 How It Works

1. **Ping Test** - Measures round-trip latency to calculate network responsiveness
2. **Download Test** - Downloads test files from CDN servers to measure download bandwidth
3. **Upload Test** - Simulates upload traffic to estimate upload capacity
4. **Jitter Calculation** - Analyzes variance in ping times for connection stability
5. **Packet Loss** - Counts failed requests to determine network reliability

### Accuracy Notes
- Results may vary based on network conditions, time of day, and server load
- For most accurate results, close other applications using bandwidth
- The test uses public CDN endpoints for cross-origin compatibility
- Desktop apps provide more accurate results than browser-based tests

---

## 🔧 Technical Details

### Technologies Used
- **HTML5** - Semantic markup with accessibility features
- **CSS3** - Responsive design with CSS variables and media queries
- **JavaScript ES6+** - Modern async/await patterns with Fetch API
- **Tailwind CSS** - Utility-first styling framework
- **Electron** - Cross-platform desktop application framework
- **Capacitor** - Native mobile app wrapper

### Performance Optimizations
- **Debounced resize handlers** for smooth window resizing
- **RequestAnimationFrame** for 60fps canvas animations
- **Visibility API** to pause animations when tab is hidden
- **Reduced motion support** for accessibility
- **Device pixel ratio scaling** for crisp rendering on HiDPI displays

### Browser Compatibility
- Full support for all modern browsers
- Graceful degradation for older browsers
- Automatic feature detection
- Keyboard navigation support
- Screen reader compatible

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/anacondy/3-SOTL-Speed-test/issues)
- **Wiki**: [Project Wiki](https://github.com/anacondy/3-SOTL-Speed-test/wiki)

---

Made with ❤️ by [Anuj Meena](https://github.com/anacondy)