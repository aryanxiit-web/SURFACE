# SURFACE. — GitHub Pages + APK setup

Your repo is named `SURFACE`, so your GitHub Pages URL is:
`https://aryanxiit-web.github.io/SURFACE/`

## Final File Structure
```
index.html                    ← app (renamed from surface.html)
manifest.json
sw.js
icons/
  icon-192.png
  icon-512.png
  icon-maskable-192.png
  icon-maskable-512.png
README.md
```

All paths are already set to `/SURFACE/` — don't change them.

## 1. Upload to GitHub
Push all 6 files (+ icons folder) to the root of your `SURFACE` repo. Keep the `icons/` subfolder.

## 2. Verify GitHub Pages is Live
1. Go to repo → **Settings** → **Pages**
2. Confirm source is `main` branch, `/ (root)` folder
3. Wait 1–2 minutes after the first push
4. Test: Open `https://aryanxiit-web.github.io/SURFACE/`
   - App should load directly (no `index.html` suffix needed) ✓
   - If 404, wait and refresh

## 3. Check the Manifest is Reachable
Before PWABuilder, manually test:
`https://aryanxiit-web.github.io/SURFACE/manifest.json`

If you see JSON with `"name"` and `"description"`, you're good.

## 4. Generate the APK with PWABuilder
1. Go to https://www.pwabuilder.com
2. Paste `https://aryanxiit-web.github.io/SURFACE/`
3. Click **Start** — it will find the manifest
4. Check the report card — all green ✓
5. Go to **Android** tab → **Generate Package**
6. Download the APK

## Troubleshooting
- **PWABuilder says manifest not found**: Check step 3 above.
- **App doesn't load at the root URL**: Pages isn't enabled. Go to Settings → Pages → enable it.
- **Icons not showing**: Confirm they're in `/icons/` at the root level.

## Updating Later
To push updates, bump the cache version in `sw.js`:
```javascript
const CACHE_NAME = 'surface-v2';  // increment the number
```
Users will get the new version on their next visit.
