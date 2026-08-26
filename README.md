# SURFACE. — GitHub Pages + APK setup

## 1. Upload to GitHub
Create a repo (e.g. `surface-app`) and upload these files keeping the folder structure:

```
surface.html
manifest.json
sw.js
index.html
icons/
  icon-192.png
  icon-512.png
  icon-maskable-192.png
  icon-maskable-512.png
```

## 2. Enable GitHub Pages
Repo → Settings → Pages → Source: `main` branch, `/ (root)` folder → Save.
Your live URL will be something like:
`https://<your-username>.github.io/surface-app/`

Wait 1–2 minutes after the first push, then open that URL and confirm
`surface.html` loads (index.html auto-redirects to it).

## 3. Generate the APK with PWABuilder
1. Go to https://www.pwabuilder.com
2. Paste your GitHub Pages URL and click **Start**
3. PWABuilder reads `manifest.json` automatically — check the manifest score is green
4. Go to the **Android** package tab → **Generate Package**
5. Download the `.apk` (or `.aab` for Play Store) it produces

## Notes
- `sw.js` caches the app so it opens even with no signal after the first load.
- If you update `surface.html` later, bump `CACHE_NAME` in `sw.js` (e.g. `surface-v2`)
  so returning users get the new version instead of the cached one.
- Icons are plain PNGs generated to match the app's dark/cyan theme — swap them
  for your own artwork any time, just keep the same filenames and sizes.
