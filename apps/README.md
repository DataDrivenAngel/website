# Block Sudoku

A block-placing puzzle on a 9×9 grid that installs as a progressive web app and works offline.

## Files

- `index.html`: the game
- `manifest.webmanifest`: app name, colors and icons for installing
- `sw.js`: service worker that caches everything for offline play
- `icons/`: app icons (regular, maskable for Android, and Apple touch icon)
- `fonts/`: Bricolage Grotesque, bundled so it works offline (SIL Open Font License, see `fonts/OFL.txt`)

## Hosting

Service workers only run over HTTPS or on `localhost`, so the app can't be installed from a file opened directly. The game itself still plays that way.

Upload the whole folder, keeping its structure, to any static host: GitHub Pages, Netlify, Cloudflare Pages, Vercel, or your own server. It works from a subfolder too, since every path is relative.

To try it on your computer:

```
cd block-sudoku
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Installing

- **Android / Chrome / Edge:** use the Install button in the game, or the browser menu's "Install app" option.
- **iPhone / iPad (Safari):** tap Share, then "Add to Home Screen".

## Updating

After changing any file, change `VERSION` in `sw.js` (for example to `block-sudoku-v2`). Players get the new version the next time they open the app while online.

## Saved data

Best score and the game in progress are stored in the browser's localStorage on each device.
