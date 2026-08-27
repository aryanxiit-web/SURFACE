# SURFACE. — GitHub Pages + APK setup

Your repo is named `SURFACE`, so your GitHub Pages URL is:
`https://aryanxiit-web.github.io/SURFACE/`

## 1. Upload to GitHub
Make sure files are at the **root** of your `SURFACE` repo (not in subfolders):

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
README.md
```

All paths in the files already point to `/SURFACE/` — don't change them.

## 2. Verify GitHub Pages is Live
1. Go to repo → **Settings** → **Pages**
2. Confirm source is `main` branch, `/ (root)` folder
3. Wait 1–2 minutes after the first push
4. Test: Open `https://aryanxiit-web.github.io/SURFACE/surface.html`
   - If it loads, you're good ✓
   - If 404, wait and refresh

## 3. Check the Manifest is Reachable
Before PWABuilder, manually test this URL:
`https://aryanxiit-web.github.io/SURFACE/manifest.json`

If you see JSON with `"name"` and `"description"` fields, proceed. If 404, the file didn't push correctly.

## 4. Generate the APK with PWABuilder
1. Go to https://www.pwabuilder.com
2. Paste `https://aryanxiit-web.github.io/SURFACE/`
3. Click **Start** — it will scan and find the manifest
4. Check the report card — all green now ✓
5. Go to **Android** tab → **Generate Package**
6. Download the APK

## Troubleshooting
- **PWABuilder says "Missing Name"**: The manifest.json wasn't found. Check step 3.
- **Manifest returns 404**: You didn't push it, or it's in the wrong folder. Push to the root.
- **Icons not showing in PWABuilder**: Make sure they're in `/icons/` at the root, not nested deeper.
- **Service worker not registering**: Confirm `sw.js` is at the root level.

## Updating Later
If you update `surface.html`, bump the cache version in `sw.js`:
```javascript
const CACHE_NAME = 'surface-v2';  // increment the number
```
This forces users to download the new version on next visit.
