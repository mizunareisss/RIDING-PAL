# Ride Visualizer

3D cycling route visualizer for Garmin **GPX / TCX** files. Drop a file onto the page and get an interactive 3D track with telemetry dashboard, path-tracking playback, heart-rate / power heatmaps, and a scrubbable timeline.

> Live site: _(pending first deploy — will update after Netlify goes live)_

## Features

- Self-contained single HTML file — no backend, no build step
- Client-side GPX / TCX parsing (auto-detect)
- 3D scene (Three.js via ESM CDN): compass, adjustable vertical exaggeration
- Telemetry dashboard: distance scrubber, elevation sparkline, HR / Power gauges
- Path-tracking playback with speed control (0.5×–5×)
- Heatmap overlay for heart rate / power
- Middle-mouse / right-click pan, scroll-wheel zoom, left-drag orbit

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

Or just double-click `index.html` — everything is static.

## Deployment workflow

This repo is wired to Netlify. Any push to `main` triggers a redeploy in ~30s.

```bash
# edit index.html (this is the source of truth)
git add index.html
git commit -m "Describe the change"
git push
# wait ~30s, refresh the live URL
```

That's the whole loop. No build command, no env vars, no CI config.

## Stack

- [Three.js](https://threejs.org/) (loaded from unpkg CDN, pinned to r160)
- Vanilla JS, vanilla CSS, no npm dependencies
