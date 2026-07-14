# 🔍 AdvancedSearch

<div align="center">

![Version](https://img.shields.io/badge/version-3.0-gold.svg?style=for-the-badge&labelColor=0A0E1A&color=F5C842)
![Platform](https://img.shields.io/badge/platform-Windows-blue.svg?style=for-the-badge&labelColor=0A0E1A&color=1A2035)
![Python](https://img.shields.io/badge/python-3.10+-blue.svg?style=for-the-badge&labelColor=0A0E1A&color=1A2035)
![License](https://img.shields.io/badge/license-Proprietary-red.svg?style=for-the-badge&labelColor=0A0E1A&color=E04848)
![Playwright](https://img.shields.io/badge/powered%20by-Playwright-green.svg?style=for-the-badge&labelColor=0A0E1A&color=4CAF82)

<br/>

**Powerful automated search engine interaction tool with intelligent navigation,**  
**three-layer vignette protection, and a custom navy + gold UI.**

<br/>

[📥 Download](#-installation) &nbsp;•&nbsp; [✨ Features](#-features) &nbsp;•&nbsp; [🎮 Usage](#-usage) &nbsp;•&nbsp; [❓ FAQ](#-faq) &nbsp;•&nbsp; [🔧 Troubleshooting](#-troubleshooting)

<br/>

</div>

---

## 🚀 What is AdvancedSearch?

AdvancedSearch is a sophisticated Playwright-powered automation tool that performs Google searches, locates your target URL in the results, and interacts with it naturally — simulating realistic human browsing behaviour throughout.

Built for maximum reliability, it handles every modern web obstacle automatically:

| Use Case | Description |
|----------|-------------|
| 📈 **SEO Testing** | Monitor and interact with your website's search result positioning |
| 🔬 **Research Automation** | Automate repetitive, multi-session search workflows |
| 📊 **Traffic Simulation** | Exercise realistic user journey flows end-to-end |
| 🛡️ **QA Verification** | Confirm search result ranking and page reachability |

---

## ✨ Features

### Core Engine

| Feature | Details |
|---------|---------|
| 🎯 **Smart Target Detection** | Scans result pages and clicks your target URL the moment it appears |
| 🔄 **VPN / IP Rotation Support** | Detects WAN IP changes via four public APIs and seamlessly restarts |
| 🤖 **Anti-Detection Layer** | Suppresses `navigator.webdriver`, spoofs plugin/language lists, removes automation flags |
| ⏱️ **Flexible Runtime** | 1–1 440 minutes, or run indefinitely until manually closed |
| 🔁 **Auto Session Recovery** | Exponential back-off restart on crash; gives up after 10 consecutive failures |
| 📄 **Multi-page SERP Navigation** | Paginate up to 10 Google result pages per cycle before resetting |

### 🛡️ Three-Layer Google Vignette Protection

AdvancedSearch v3.0 introduces a dedicated, layered defence against Google's vignette interstitial ads (`#google_vignette`):

```
Layer 1 – Route Interceptor   →  Aborts vignette requests before any byte loads
Layer 2 – Frame Navigator     →  framenavigated event fires _close_vignette() instantly
Layer 3 – Overlay Dismissal   →  Every dismiss_overlays() call checks the URL first
```

Each layer uses a four-strategy waterfall:

1. Click the **×** button inside the vignette iframe
2. Strip the `#google_vignette` fragment and navigate to the **clean URL**
3. Call `page.go_back()` to return to the previous page
4. Send the **Escape** key as a last resort

Vignette tabs opened by redirects are also detected and **closed automatically**.

### Intelligent Overlay Handling

- ✅ GDPR / cookie consent banners (23 selectors)
- ✅ Fullscreen interstitial ad vignettes (DOM + iframe)
- ✅ Generic modal and popup dialogs (13 selectors)
- ✅ Body `overflow: hidden` interstitial trick
- ✅ JavaScript click fallback when normal click fails

### Organic Browsing Simulation

- Random dwell time on target pages (30–90 seconds)
- Random wait between internal link clicks (60–120 seconds)
- Full-page scroll down then back to top
- Internal link selection from up to 5 shuffled candidates
- Visited URL tracking prevents duplicate navigation

### Custom Navy + Gold UI

A fully custom-drawn Tk interface — no OS title bar, complete colour control:

- 🟦 Deep navy background (`#0A0E1A`) with layered surface cards
- 🟡 Gold accent (`#F5C842`) borders, buttons, and strip markers
- ✨ Focus glow on input fields
- 🖱️ Drag-to-move windows, minimize, red-hover close button
- 📊 Animated gold progress bar during long operations
- 🪟 Three-step wizard for clean input collection

---

## 📦 Installation

### Pre-built Executable

1. Go to the [**Releases**](../../releases) page
2. Download the latest `AdvancedSearch.exe`
3. Place `AdvancedSearch.ico` in the **same folder**
4. Double-click to run — no Python or dependencies required

---

## 🎮 Usage

### Step-by-Step Wizard

Launch the application and follow the three-step GUI wizard:

**Step 1 of 3 — Search Keyword**
```
Enter the keyword or phrase to search on Google.

Example:  best organic coffee beans
```

**Step 2 of 3 — Target URL**
```
Enter the target URL to find in results.
Do NOT include https:// — bare hostname only.

Example:  mycoffeesite.com/shop
```

**Step 3 of 3 — Session Duration**
```
How many minutes should the session run?
Enter 0 to run until you close the window.
Maximum: 1440 (24 hours).

Default: 60
```

### What Happens After You Click OK

```
1.  Browser window opens → navigates to Google
2.  Keyword is typed and submitted
3.  SERP pages scanned for your target URL
4.  Target found → clicked → page loads
5.  Overlays / vignettes dismissed automatically
6.  Page scrolled naturally, internal links browsed
7.  Random wait (60–120 s) → next internal link
8.  After dwell period → return to Google → repeat
9.  On IP change → session restarts transparently
10. On runtime expiry → browser closes, profile cleaned
```

### Keyboard Shortcuts (GUI)

| Key | Action |
|-----|--------|
| `Enter` | Confirm / OK |
| `Escape` | Cancel / close dialog |

---

## 📋 System Requirements

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| **OS** | Windows 10 64-bit | Windows 11 |
| **Python** | 3.10 | 3.12+ |
| **RAM** | 4 GB | 8 GB |
| **Disk Space** | 600 MB | 1 GB |
| **Network** | Broadband | Broadband + VPN |

> ✅ Chromium is downloaded and cached automatically on first run.  
> ✅ No Chrome, Edge, or Firefox installation required.

---

## 📁 File & Folder Layout

```
AdvancedSearch/
├── search_automation.py      ← main script
├── AdvancedSearch.ico        ← UI icon (must be in same folder)
│
C:\AdvancedSearch\            ← runtime root (created automatically)
├── logs\
│   └── session_YYYYMMDD_HHMMSS.log
├── browsers\
│   └── chrome-win\
│       └── chrome.exe        ← auto-downloaded Chromium
└── chrome_profile\           ← persistent browser profile (cleaned on exit)
```

---

## 📊 Log Reference

Logs are written to `C:\AdvancedSearch\logs\` with full timestamps.  
Each session creates a new file: `session_20250714_143000.log`

```
2025-07-14 14:30:01 [INFO    ] – AdvancedSearch Engine – starting
2025-07-14 14:30:02 [INFO    ] – Chromium found at C:\AdvancedSearch\browsers\...
2025-07-14 14:30:05 [INFO    ] – Initial WAN IP: 203.0.113.42
2025-07-14 14:30:06 [INFO    ] – Timer armed: 60 minute(s)
2025-07-14 14:30:08 [INFO    ] – Results loaded for 'best organic coffee beans'
2025-07-14 14:30:09 [INFO    ] – Vignette route interceptor installed
2025-07-14 14:30:45 [INFO    ] – Target: https://mycoffeesite.com/shop
2025-07-14 14:30:47 [INFO    ] – Cookie banner dismissed via 'button:has-text("Accept")'
2025-07-14 14:30:48 [INFO    ] – Dwelling 54.3 s on target page
2025-07-14 14:31:42 [INFO    ] – Internal link: https://mycoffeesite.com/shop/espresso
2025-07-14 14:31:44 [INFO    ] – Waiting 87.6 s before next click
2025-07-14 14:33:11 [INFO    ] – IP rotation: 203.0.113.42 → 198.51.100.7
2025-07-14 14:33:16 [INFO    ] – New session (IP: 198.51.100.7)
```

**Log levels:**

| Level | Meaning |
|-------|---------|
| `INFO` | Normal operation milestones |
| `WARNING` | Recoverable issues (timeouts, IP failures) |
| `ERROR` | Action failed but session continues |
| `CRITICAL` | Unrecoverable — tool will stop |
| `DEBUG` | Verbose detail (file only, not console) |

---

## ❓ FAQ

<details>
<summary><b>Is this safe to use?</b></summary>

The tool runs a standard Chromium browser locally on your machine. All activity is logged to `C:\AdvancedSearch\logs\` for complete transparency. No data is transmitted to external servers by AdvancedSearch itself.

Users are responsible for complying with Google's Terms of Service and any applicable laws. See the [Disclaimer](#️-disclaimer) section.
</details>

<details>
<summary><b>Why does it check my IP address?</b></summary>

IP monitoring enables seamless VPN rotation support. When your WAN IP changes (e.g. your VPN switches servers), AdvancedSearch detects it within 15 seconds, re-establishes a baseline, and restarts the session — preserving all previously visited URLs so work is not duplicated.

Four independent public APIs are tried in sequence so a single API outage does not trigger a false rotation event.
</details>

<details>
<summary><b>What is a Google vignette and how is it handled?</b></summary>

A Google vignette is a fullscreen interstitial ad that appears when navigating from Google search results to certain pages. It shows as a URL fragment like `https://example.com/page#google_vignette`.

AdvancedSearch v3.0 blocks these at three levels:

1. **Route level** — the request is aborted before the browser renders anything
2. **Navigation level** — a `framenavigated` listener fires the moment the main frame lands on a vignette URL
3. **Overlay level** — every overlay-check routine inspects the current URL first

A four-strategy waterfall (iframe click → clean URL → go back → Escape) handles any that slip through.
</details>

<details>
<summary><b>Can I run multiple instances?</b></summary>

Not simultaneously. All instances share the same Chrome profile directory (`C:\AdvancedSearch\chrome_profile\`) and will conflict. Run one instance at a time, or modify `_PROFILE_DIR` in the source to use separate paths.
</details>

<details>
<summary><b>What if Google shows a CAPTCHA?</b></summary>

AdvancedSearch detects standard CAPTCHA elements and aborts the current search cycle, then retries after a short delay. Complex image-selection CAPTCHAs require manual intervention — you can solve them directly in the visible browser window and the session will continue automatically.
</details>

<details>
<summary><b>The window appears but I can't move it.</b></summary>

Ensure you are running v3.0 or later. Earlier versions had a drag bug where `geometry()` was called on a `Frame` instead of the `Toplevel`. This was fixed by resolving the real window via `winfo_toplevel()` and using `event.x_root`/`event.y_root` for smooth, jitter-free dragging.
</details>

<details>
<summary><b>Why is the EXE file large?</b></summary>

The executable bundles Python, all dependencies, and a complete Chromium distribution. This is intentional — it means zero setup for end users and guarantees a consistent, tested environment.
</details>

<details>
<summary><b>How do I stop the tool early?</b></summary>

Any of the following work:
- Click the **✕** button on the AdvancedSearch dialog (if still open)
- Close the Chromium browser window
- Press `Ctrl+C` in the console window
- Wait for the configured runtime to expire

On exit the browser profile is cleaned up automatically.
</details>

---

## 🔧 Troubleshooting

| Symptom | Likely Cause | Solution |
|---------|-------------|----------|
| **Browser setup failed** | No internet or CDN unreachable | Check connection; try again after 60 s |
| **Tool closes immediately** | Startup exception | Run from a terminal to read the error |
| **Target URL never found** | URL not in top 100 results | Verify keyword relevance; check URL format (no `https://`) |
| **Vignette not dismissed** | New vignette format | Check logs for "strategies exhausted"; report via Issues |
| **CAPTCHA loop** | Google flagging the session | Solve manually in the browser; reduce session frequency |
| **High RAM usage** | Chromium baseline | Normal — close other applications; 8 GB recommended |
| **Drag doesn't work** | Running an older build | Update to v3.0+ which fixes the `Frame.geometry` bug |
| **IP check always fails** | All four IP APIs down | Rare; tool will treat 4 consecutive failures as an IP change |

---

## ⚙️ Configuration Reference

Key timing constants can be adjusted at the top of `search_automation.py`:

```python
_CLICK_WAIT_MIN     = 60.0    # seconds – minimum wait between organic clicks
_CLICK_WAIT_MAX     = 120.0   # seconds – maximum wait between organic clicks
_DWELL_MIN          = 30.0    # seconds – minimum time on target page
_DWELL_MAX          = 90.0    # seconds – maximum time on target page
_IP_CHECK_INTERVAL  = 15.0    # seconds – how often to poll WAN IP
_IP_FAILURE_LIMIT   = 4       # consecutive IP fetch failures → treat as rotation
_MAX_SEARCH_PAGES   = 10      # SERP pages to scan before resetting
_MAX_SESSION_ERRORS = 5       # consecutive errors before session restart
```

---

## ⚠️ Disclaimer

This tool is provided for **educational and legitimate testing purposes only**.  
Users are solely responsible for ensuring their use complies with:

- Google's [Terms of Service](https://policies.google.com/terms)
- The target website's terms of service and `robots.txt`
- All applicable local, national, and international laws

**The developers assume no liability for misuse or any consequences arising from the use of this software.**

---

## 📝 Changelog

### v3.0 — Current
- **Three-layer Google vignette defence** — route interceptor + frame listener + overlay check
- **Four-strategy vignette waterfall** — iframe click → clean URL → go_back → Escape
- **Vignette tab auto-close** — detects and closes tabs opened by vignette redirects
- **Custom navy + gold UI** — fully borderless windows with draggable title bar
- **Fixed drag-to-move** — `winfo_toplevel()` + `x_root`/`y_root` coordinate fix
- All "SearchBot" references renamed to **AdvancedSearch**
- Runtime root moved to `C:\AdvancedSearch\`
- `_ICON_FILE` resolved relative to script, not CWD

### v2.0
- Migrated from Selenium to **Playwright** for improved reliability
- Automatic Chromium bundling — no Chrome installation required
- Enhanced cookie banner and ad dismissal (23 + 13 selectors)
- Improved anti-detection (`navigator.webdriver`, plugins, languages)
- Automatic session recovery with exponential back-off
- Structured logging with per-session log files

### v1.0
- Initial release with Selenium
- Basic search and single-click functionality

---

<div align="center">

<br/>

Made with ☕ and a lot of `await asyncio.sleep()`

<br/>

![Navy](https://img.shields.io/badge/%20-0A0E1A?style=for-the-badge&color=0A0E1A)
![Gold](https://img.shields.io/badge/%20-F5C842?style=for-the-badge&color=F5C842)
![Navy](https://img.shields.io/badge/%20-0A0E1A?style=for-the-badge&color=0A0E1A)

<br/>

[🐛 Report Bug](../../issues) &nbsp;•&nbsp; [💡 Request Feature](../../issues) &nbsp;•&nbsp; [📖 View Source](../../)

<br/>

</div>
