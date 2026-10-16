# Everwell Fitness Tracker — Version 2

Everwell is a zero-cost, offline-first personal fitness tracker. It records food, editable recipes, activity, daily goals, weight and waist measurements. There is no account, analytics service, advertising code or cloud database.

## Privacy and backups

- Entries are stored only in the current browser using local storage.
- Clearing browser/site data removes those entries.
- Use **Settings → Export backup** regularly and keep the JSON file somewhere private.
- Importing a backup replaces the data currently stored in that browser.
- Publishing the app files does **not** publish your diary: the app files are public, but each user's local entries are not part of those files.

## Try it on this Windows PC

The app should be served by a small local web server rather than opened by double-clicking `index.html`; installation and offline support need an HTTP address. Codex can launch the preview for you while we work.

## Deploy to GitHub Pages (free)

1. Create a new GitHub repository, for example `everwell-tracker`. It can be public. Do not add any exported backup JSON files.
2. Upload the contents of this folder so `index.html` is at the repository root.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub to show the live Pages address. Open that address on the iPhone in Safari.
7. In Safari, use **Share → Add to Home Screen**.

After an update, refresh the site once while online. The service worker will cache the new files for offline use.

## Apple Health and Shortcuts — later phase

A normal website cannot silently read HealthKit. The practical zero-cost route is an iPhone Shortcut that reads only the Health fields you choose, then passes or exports them in a format Everwell can import. We should build and test that Shortcut on the iPhone before treating it as a dependable sync. Until then, activity remains manual and no automatic HealthKit syncing is claimed.

## Files

- `index.html` — app screens and forms
- `styles.css` — responsive desktop/iPhone design
- `app.js` — local data, calculations, editing, export/import and charts
- `manifest.webmanifest` and `icon.svg` — installable app metadata
- `sw.js` — offline cache
