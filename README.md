# My Little Life — Web App

A mobile-friendly personal organizer that includes:
- Journal entries with categories and pictures
- Quick notes and categories
- Daily habit tracker
- Mood check-ins and history
- Period dates and notes
- Income and expense tracker (₹)
- To-do list with due dates and priorities
- Food diary with optional calorie and protein estimates
- Monthly calendar for events, birthdays, appointments, bills and yearly repeats
- JSON backup export
- Installable PWA shell and offline app shell caching

## Quick test on your computer
1. Extract the ZIP.
2. Open `index.html` in a modern browser for a basic local test.
3. For installability/offline caching, serve it over HTTPS or localhost; service workers do not work from ordinary `file://` URLs.

## Publish it for Android home-screen installation (free static hosting)
A simple option is GitHub Pages:
1. Create/sign in to a GitHub account.
2. Create a new public repository, for example `my-little-life`.
3. Upload `index.html`, `manifest.webmanifest`, `sw.js`, and `icon.svg` to the repository root.
4. In repository **Settings → Pages**, choose deploy from the `main` branch and `/ (root)`, then save.
5. Wait for GitHub Pages to provide the published HTTPS URL.
6. Open that URL in Chrome on your Android phone.
7. Open Chrome's three-dot menu and choose **Install app** or **Add to Home screen** (wording varies by Chrome version).

For best PWA/offline support, add this snippet just before `</body>` in `index.html` (it is included in this project's app file):
`if ("serviceWorker" in navigator) { window.addEventListener("load", () => navigator.serviceWorker.register("./sw.js")); }`

## Data and privacy notes
- This prototype stores records in the browser's local storage on that device/browser.
- It does not upload data to a server or sync across devices.
- Use **Export backup** regularly. The downloaded JSON file contains personal information and any photos embedded in journal entries; store it somewhere private.
- Clearing browser data can delete the app's saved records. Export before clearing data or switching phones.
- Photo uploads are limited to 5 per entry and 900 KB per photo to reduce local storage problems.
- Browser storage capacity varies. A full production version should use IndexedDB for photos, encryption/secure lock, import/restore, and automated backups.
- Period predictions and nutrition estimates are informational only; this app is not a medical tool.
- Calendar events are stored in the app. This prototype does not send phone notifications/reminders.

## Restore/import
The current version exports a JSON backup but does not yet provide an in-app restore/import button. Keep the backup file safe.
