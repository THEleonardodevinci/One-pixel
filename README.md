# One-Pixel Camera

A camera that destroys the photo and keeps only its average color. Every capture becomes a specimen: one hex code, a timestamp, a note, and a place. Over time, your life becomes a gradient.

**The photo is never stored.** It's averaged down to a single color in your browser, then discarded.

## Features

- **Capture** — opens your phone camera (or photo picker), averages the image to one color
- **Specimen catalog** — each color gets a note, a location (typed or via GPS), and a nearest color name ("terracotta," "seafoam," "storm")
- **Gradient strip** — your full history as tappable bands, with a smooth-blend toggle
- **Months view** — average color per month with mini-strips
- **Stats** — the average of everything, your lightest / darkest / boldest moments
- **Search** — filter specimens by note, place, hex, or color name
- **Exports** — download the gradient as a PNG, or any single specimen as a shareable card
- **Backup** — export/import your whole catalog as JSON (data lives in localStorage, device-only)

## Run locally

```bash
npm install
npm run dev
```

Open http://localhost:5173

## Deploy to GitHub + Vercel

1. **Create the repo**

   ```bash
   git init
   git add .
   git commit -m "One-Pixel Camera"
   ```

   Create a new repository on github.com (no README/gitignore — you have them), then:

   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/one-pixel-camera.git
   git branch -M main
   git push -u origin main
   ```

2. **Deploy on Vercel**

   - Go to vercel.com → **Add New → Project**
   - Import the `one-pixel-camera` repo
   - Vercel auto-detects Vite — leave build settings as-is (`npm run build`, output `dist`)
   - Click **Deploy**

   Every push to `main` redeploys automatically.

3. **Use it on your phone** — open the Vercel URL, then "Add to Home Screen" for an app-like experience. The camera and GPS both require HTTPS, which Vercel provides by default.

## Notes

- Data is stored in `localStorage` on the device you use — there's no server and no account. Export a backup before switching phones or clearing browser data.
- GPS "locate" stores rounded coordinates only; you can always type a place name instead.

## Stack

Vite + React, no other runtime dependencies. Fonts: Archivo (display) + IBM Plex Mono (everything else).
