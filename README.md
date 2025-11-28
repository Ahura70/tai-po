# Wang Fuk Court Fire Relief App (大埔宏福苑火災援助)

![Status](https://img.shields.io/badge/Status-Active-success) ![PWA](https://img.shields.io/badge/PWA-Ready-blue) ![License](https://img.shields.io/badge/License-MIT-green)

A lightweight, offline-capable Progressive Web App (PWA) designed to provide immediate information regarding the Wang Fuk Court fire tragedy in Tai Po, Hong Kong. This tool aggregates resources for victims, volunteers, and donors.

**中文簡介：**這是一個輕量級、可離線使用的網頁應用程式（PWA），旨在為大埔宏福苑火災提供即時資訊整合，方便災民、義工及捐贈者尋找所需資料。

## 🚨 Key Features (主要功能)

*   **Offline Capable:** Works without internet after the first load (Service Worker enabled).
*   **Multilingual:** Auto-detects and supports **Traditional Chinese, English, Tagalog, and Bahasa Indonesia** (Crucial for residents and domestic helpers).
*   **Voice Search:** Accessible voice search for finding resources quickly.
*   **One-Tap Actions:** Click to copy bank details or dial emergency numbers immediately.
*   **Zero Dependencies:** Pure HTML/CSS/JS. No frameworks, no build steps, high performance on low-end devices.

## 📂 Project Structure (檔案結構)

The project consists of only three files to ensure easy deployment:

1.  `index.html` - The core application logic, UI, and data.
2.  `manifest.json` - Configuration to make the app installable on mobile devices.
3.  `sw.js` - Service Worker script to enable offline functionality.

## 🚀 Quick Start (快速開始)

### Option 1: Run Locally (本地運行)

You cannot simply double-click `index.html` for the PWA features to work (Service Workers require HTTPS or localhost).

1.  Clone or download this repository.
2.  Open the folder in a terminal.
3.  Run a local server.
    *   **Python 3:** `python -m http.server 8000`
    *   **Node.js:** `npx serve`
    *   **VS Code:** Use the "Live Server" extension.
4.  Open `http://localhost:8000` in your browser.

### Option 2: Deploy to Production (1-Minute Deploy)

This site is static and can be hosted anywhere for free.

*   **Netlify Drop (Recommended):** Drag and drop the project folder to [app.netlify.com/drop](https://app.netlify.com/drop).
*   **GitHub Pages:** Push to a repo and enable GitHub Pages in Settings.
*   **Vercel:** Import via Git or CLI.

## 📝 How to Update Information (如何更新資訊)

All data is contained within `index.html` to keep the app fast and simple.

1.  Open `index.html`.
2.  Search for the `const resources = { ... }` object (around line 250).
3.  Update the arrays for each language (`zh`, `en`, etc.).
4.  **Important:** Update the "Last Updated" date in the HTML:
    ```html
    <div ... id="lastUpdated">Updates: 2025-11-28</div>
    ```

### Data Format Example

```javascript
{
  icon: '💰',
  title: 'Service Name',
  desc: 'Short description',
  keywords: ['keyword1', 'keyword2'], // Used for search
  info: ['Extra detail line 1', 'Extra detail line 2'], // Optional yellow box info
  contacts: [
    { l: 'Label', v: 'Value (Phone/Account)' }
  ]
}
