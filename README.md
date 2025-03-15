# AdvancedSearch

AdvancedSearch is designed to automate Google searches, locate a specific target URL, and interact with it intelligently. Built with Selenium, it includes features like IP change detection, robust error handling, and customizable runtime, making it ideal for web scraping, SEO testing, or automated browsing tasks.

## Features
- **Targeted Search**: Searches Google for a user-specified keyword and navigates to a target URL (e.g., `nfl.com`).
- **IP Change Detection**: Restarts the search if the WAN IP changes, without resetting the runtime timer.
- **Click Reliability**: Handles "element not interactable" errors with size checks and JavaScript fallbacks.
- **Session Recovery**: Automatically recreates the browser session if it crashes (e.g., `invalid session id`).
- **Customizable Runtime**: Runs for a specified duration (0-1440 minutes) or until manually stopped.
- **Logging**: Detailed logs saved to `C:\logs` for debugging and monitoring.

## Prerequisites
- Google Chrome installed

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/AdvancedSearch.git
   cd AdvancedSearch
