# 🔍 AdvancedSearch

<div align="center">

![Version](https://img.shields.io/badge/version-2.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![License](https://img.shields.io/badge/license-Proprietary-red.svg)

**Powerful automated search engine interaction tool with intelligent navigation and anti-detection capabilities.**

[Download](#installation) • [Features](#features) • [Usage](#usage) • [FAQ](#faq)

</div>

---

## 🚀 What is AdvancedSearch?

AdvancedSearch is a sophisticated automation tool that performs Google searches, locates your target URL in search results, and interacts with it naturally. Built for maximum reliability, it simulates human-like browsing behavior while handling modern web challenges like cookie banners, CAPTCHAs, and ad overlays.

Perfect for:
- 📈 **SEO Testing** - Monitor your website's search visibility
- 🔬 **Research Automation** - Automate repetitive search tasks
- 📊 **Traffic Analysis** - Test user journey flows
- 🛡️ **Quality Assurance** - Verify search result positioning

---

## ✨ Features

### Core Capabilities
| Feature | Description |
|---------|-------------|
| 🎯 **Smart Target Detection** | Automatically finds and clicks your target URL across multiple search result pages |
| 🔄 **IP Change Detection** | Detects WAN IP changes and seamlessly restarts without losing progress |
| 🤖 **Anti-Detection** | Built-in measures to appear as a regular browser session |
| ⏱️ **Flexible Runtime** | Run for 1-1440 minutes or until manually stopped |

### Intelligent Automation
- **Cookie Banner Handling** - Automatically dismisses GDPR/cookie consent popups
- **Ad Vignette Dismissal** - Handles fullscreen interstitial ads
- **Human-like Behavior** - Random delays, natural scrolling, and varied click patterns
- **Multi-page Navigation** - Searches through multiple result pages to find your target
- **Session Recovery** - Automatically recovers from browser crashes

### Robust Error Handling
- ✅ Click reliability with JavaScript fallbacks
- ✅ Timeout recovery and retry logic
- ✅ Detailed logging for troubleshooting
- ✅ Graceful cleanup on exit

---

## 📦 Installation

### Download Executable

1. Go to the [**Releases**](../../releases) page
2. Download the latest `AdvancedSearch.exe`
3. Run the executable - **no installation required!**

> 💡 The browser is bundled with the application. No need to install Chrome or any other dependencies.

---

## 🎮 Usage

1. **Launch** the application by double-clicking `AdvancedSearch.exe`
2. **Enter your search keyword** (e.g., "best desktop emulator")
3. **Enter your target URL** (e.g., `rec0m88.com` - without https://)
4. **Set runtime** in minutes (0 = run until manually closed, max 1440)
5. **Let it run!** The tool will search, find your URL, and interact naturally

### Example Input

Keyword: "organic coffee beans"
Target URL: mycoffeesite.com
Runtime: 60 minutes

### What Happens Next
1. A browser window opens and navigates to Google
2. Your keyword is searched automatically
3. The tool scans through search result pages looking for your target URL
4. When found, it clicks through and browses naturally with random delays
5. Process repeats until runtime expires or you close the application

---

## 📋 System Requirements

| Requirement | Details |
|-------------|---------|
| **OS** | Windows 10 / Windows 11 |
| **RAM** | 4GB minimum (8GB recommended) |
| **Disk Space** | ~500MB for browser cache |
| **Network** | Active internet connection |

> ✅ **No additional software needed** - everything is bundled!

---

## 📁 File Locations

| Item | Location |
|------|----------|
| Activity Logs | `C:\logs\search_*.log` |
| Browser Profile | `C:\logs\chrome_profile` |
| Browser Data | `C:\logs\playwright_browsers` |

---

## 📊 Logging

All activity is logged to `C:\logs` with timestamps for easy monitoring and debugging:

2024-01-15 10:30:45 - INFO - Performing search.
2024-01-15 10:30:52 - INFO - Target URL found on page 2
2024-01-15 10:31:15 - INFO - Successfully dismissed cookie banner
2024-01-15 10:31:45 - INFO - Scrolling page.
2024-01-15 10:32:30 - INFO - Waiting 75.43 seconds before next click

---

## ❓ FAQ

<details>
<summary><b>Is this safe to use?</b></summary>

Yes! The tool runs a standard Chromium browser with anti-detection measures. All activity is logged locally for complete transparency. No data is sent to external servers.
</details>

<details>
<summary><b>Why does it check my IP address?</b></summary>

IP detection is used to restart searches when your VPN or network changes IP. This ensures consistent behavior and allows the tool to adapt to network changes automatically.
</details>

<details>
<summary><b>Can I run multiple instances?</b></summary>

Running multiple instances simultaneously is not recommended as they share the same browser profile directory and may conflict with each other.
</details>

<details>
<summary><b>What if Google shows a CAPTCHA?</b></summary>

The tool will attempt to handle simple CAPTCHAs automatically. For complex CAPTCHAs (like image selection), manual intervention may be required. The tool will wait and retry.
</details>

<details>
<summary><b>Why is the EXE file large?</b></summary>

The executable includes a complete Chromium browser and all necessary dependencies bundled together. This ensures the tool works out-of-the-box without requiring any additional installations.
</details>

<details>
<summary><b>How do I stop the tool?</b></summary>

You can either:
- Close the browser window
- Wait for the runtime to expire
- Press Ctrl+C in the console window (if visible)
</details>

<details>
<summary><b>The browser closed unexpectedly. What happened?</b></summary>

Check the logs at `C:\logs\` for details. The tool has automatic session recovery and will attempt to restart if a crash occurs during the configured runtime.
</details>

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| **"Browser setup timed out"** | Check your internet connection and try again |
| **Tool closes immediately** | Run from command prompt to see error messages |
| **Can't find target URL** | Verify the URL format (no https://) and check if the page ranks for your keyword |
| **Slow performance** | Close other applications to free up RAM |

---

## ⚠️ Disclaimer

This tool is provided for educational and legitimate testing purposes only. Users are responsible for ensuring their use complies with:
- Google's Terms of Service
- Applicable local laws and regulations
- Website terms of service

The developers assume no liability for misuse or any consequences arising from the use of this software.

---

## 📝 Changelog

### v2.0
- Migrated from Selenium to Playwright for improved reliability
- Added automatic browser bundling - no Chrome installation required
- Enhanced cookie banner and ad dismissal
- Improved anti-detection measures
- Added automatic session recovery
- Better error handling and logging

### v1.0
- Initial release with Selenium
- Basic search and click functionality

---

<div align="center">

**Made with ❤️ for automation enthusiasts**

⭐ Star this repo if you find it useful!

[Report Bug](../../issues) • [Request Feature](../../issues)

</div>
