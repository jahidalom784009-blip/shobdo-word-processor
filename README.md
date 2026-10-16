# শব্দ (Shobdo) — Personal Word Processor

A phone-friendly Progressive Web App for writing Bangla and English.

## Run locally
Because service workers require a secure context, use a local web server rather than opening `index.html` directly.
For example, with Python installed:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000`.

## Publish with GitHub Pages
1. Create a public repository on GitHub.
2. Upload all files in this folder to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/ (root)`, then Save.
6. Wait for GitHub Pages to publish the site and open the HTTPS URL it provides.

## Files
- `index.html`: editor UI, formatting, font import/storage, PDF export.
- `manifest.json`: PWA install metadata.
- `sw.js`: offline shell caching.
- `icon-192.png`, `icon-512.png`: PWA icons.

## Notes
- PDF export uses html2canvas + jsPDF from a CDN on first use, so internet is needed until those libraries are cached (the current service worker caches only same-origin files).
- PDF pages are rasterized to preserve the browser's rendered Bangla shaping; selectable/searchable PDF text is not guaranteed.
- Built-in Bangla font options are listed in the editor, but actual font availability depends on the device unless you import font files or load web fonts.
- Local autosave is browser-local; export/backup important documents.
