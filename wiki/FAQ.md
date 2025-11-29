# Frequently Asked Questions

## General Questions

### What is Silence of the Lags?
Silence of the Lags is a free, open-source internet speed testing application. It measures your download speed, upload speed, ping, jitter, and packet loss with an elegant, minimal interface.

### Is it free to use?
Yes! The application is completely free and open-source under the MIT license. There are no ads, subscriptions, or hidden fees.

### Does it collect my data?
No. All speed tests run entirely in your browser or local application. No personal data, IP addresses, or test results are collected or stored on any server.

### Why is it called "Silence of the Lags"?
It's a playful reference to eliminating lag (network latency issues) while also being a nod to a famous movie title. The dark, minimalist design reinforces this theme.

## Speed Test Questions

### How accurate is the speed test?
The test is designed to be as accurate as possible within browser limitations. For the most accurate results:
- Use the desktop application
- Connect via Ethernet
- Close other bandwidth-using applications
- Test at different times

### Why are my results different from other speed tests?
Different speed tests may show different results because:
- They use different servers
- They measure at different times
- They use different testing methodologies
- Network conditions vary moment to moment

Our test uses globally-distributed CDN servers for consistent results worldwide.

### What's a good internet speed?
| Speed | Suitable For |
|-------|-------------|
| 1-5 Mbps | Basic browsing, email |
| 5-25 Mbps | SD streaming, casual gaming |
| 25-100 Mbps | HD streaming, video calls |
| 100-500 Mbps | 4K streaming, fast downloads |
| 500+ Mbps | Multiple heavy users |

### What's the difference between Mbps and MB/s?
- **Mbps** (Megabits per second): Standard for measuring internet speed
- **MB/s** (Megabytes per second): Standard for file sizes
- **Conversion**: 1 MB/s = 8 Mbps

Our app shows both for your convenience.

### What is ping?
Ping (latency) is the time it takes for data to travel from your device to a server and back, measured in milliseconds (ms). Lower is better.

- **< 20ms**: Excellent for gaming
- **20-50ms**: Good for most uses
- **50-100ms**: Noticeable in real-time apps
- **> 100ms**: May cause lag issues

### What is jitter?
Jitter is the variation in ping times. High jitter means inconsistent connection quality, which can cause problems for video calls and gaming even if average ping is low.

### What is packet loss?
Packet loss is the percentage of data that doesn't reach its destination. Any packet loss can cause issues:
- **0%**: Perfect
- **< 1%**: Usually acceptable
- **1-5%**: May cause issues
- **> 5%**: Significant problems

## Platform Questions

### Which platforms are supported?
- **Web**: Any modern browser (Chrome, Firefox, Safari, Edge)
- **Desktop**: Windows 10+, macOS 10.15+, Linux (Ubuntu 18.04+)
- **Mobile**: Android 7.0+, iOS 13+

### Why is there no iOS app yet?
iOS apps require Apple Developer Program membership and App Store review. We're working on it! For now, use the web version in Safari.

### Can I use it on my smart TV?
If your TV has a web browser, you can try the web version. However, TV browsers are often limited and may not work perfectly.

### Does it work offline?
No, you need an internet connection to test your internet speed. The app will show "Offline" status if disconnected.

## Technical Questions

### Why does the test use CDN servers?
We use Content Delivery Network (CDN) servers because:
1. They're globally distributed for low latency
2. They support CORS for browser access
3. They're reliable and fast
4. No need for our own server infrastructure

### Is the source code available?
Yes! The project is open-source on GitHub:
https://github.com/anacondy/3-SOTL-Speed-test

### Can I contribute?
Absolutely! We welcome contributions:
1. Fork the repository
2. Make your changes
3. Submit a pull request

### Can I host my own version?
Yes! Clone the repository and host it on any web server. The app is entirely client-side.

## Troubleshooting

### The test won't start
1. Check your internet connection
2. Disable ad blockers
3. Try a different browser
4. Clear cache and cookies

### Results seem wrong
1. Test at different times
2. Close other apps using bandwidth
3. Try wired connection
4. Compare with other speed tests

### The app is slow/laggy
1. Close other browser tabs
2. Update your browser
3. Check if your device meets minimum requirements
4. The app respects reduced motion preferences

For more troubleshooting, see the [Troubleshooting Guide](Troubleshooting.md).
