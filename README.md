# Xpns — Daily Expense Tracker

A single-file installable web app (PWA) that tracks expenses by site/location and category,
with support for AED, INR, USD, EUR, GBP, SAR.

## Files
- `index.html` — the whole app (HTML + JS, no external dependencies)
- `manifest.json` — makes it installable as an app
- `sw.js` — service worker, caches the app so it works offline
- `icons/` — app icons (192, 512, and a maskable 512 for Android adaptive icons)

Everything is fully self-contained — no CDN, no external scripts, no internet needed once
loaded. This also means it will work reliably inside the WebView used by the packaged
Android app.

Data is stored in the browser's `localStorage`, on-device only.

---

## Step 1 — Put it on the web (GitHub Pages)

You already have a GitHub Pages setup from "My Wallet" (username `abhinavepsaji8`), so this
is the same flow:

1. Create a new repo, e.g. `xpns-app`.
2. Upload all the files in this folder (`index.html`, `manifest.json`, `sw.js`, `icons/`) to the repo root — keep the `icons/` folder structure as-is.
3. Go to repo **Settings → Pages**, set source to the `main` branch, root folder.
4. Wait a minute, then open `https://abhinavepsaji8.github.io/xpns-app/`.
5. Confirm it loads and looks right on your phone browser first.

## Step 2 — Package it as an Android APK (PWABuilder)

1. Go to https://www.pwabuilder.com
2. Paste your GitHub Pages URL (e.g. `https://abhinavepsaji8.github.io/xpns-app/`) and hit **Start**.
3. PWABuilder will read `manifest.json` and confirm it's installable — it should show your
   navy icon automatically.
4. Click **Package for stores → Android**.
5. Keep the default settings (Package ID like `com.abhinavepsaji.xpns`, or customize it).
6. Download the generated `.apk` (or `.aab` if you want to publish to Play Store).
7. Transfer the `.apk` to your Android phone and install it directly (enable "install from
   unknown sources" if prompted), or upload the `.aab` to Google Play Console if you want it
   listed on the Play Store.

## Notes
- Because everything is stored in `localStorage` on-device, data won't sync between your
  phone and any other device/browser — it's local to wherever you open the app.
- If you later want cloud sync (e.g. across your phone and desktop), that would need a small
  backend (Firebase is the easiest option) — let me know if you want that added.
