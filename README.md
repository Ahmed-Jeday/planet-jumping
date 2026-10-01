# Planet Jumping

Interactive Solar System explorer. Travel from Mercury to Neptune through a cinematic portal, with NASA/ESA planetary data, side-by-side comparisons, and a canvas-driven 3D viewport.

Live: https://ahmed-jeday.github.io/planet-jumping/

## Features

- Warp between all 8 planets with full-screen video transitions
- Canvas portal with perspective projection (no Three.js, no frameworks)
- Scientific dossiers: diameter, gravity, day length, moons, mass, composition, missions
- Planet comparator with visual metric bars
- Solar System directory for direct jumps
- Procedural Web Audio (ambient drone + warp sweep)
- Eco / low-power mode (caps DPR, disables heavy filters)
- Keyboard navigation and custom cursor
- Procedural planet fallback if a video fails to load

## Stack

Single-file vanilla HTML/CSS/JavaScript. No build step, no dependencies.

## Project structure

```
planet-jumping/
├── index.html          App (UI, styles, engine)
├── assets/             Videos, stills, logo
│   ├── mars-background.mp4
│   ├── to-Mercury.mp4
│   ├── to-venus.mp4
│   ├── to-earth.mp4
│   ├── to-mars.mp4
│   ├── to-Jupiter.mp4
│   ├── to-Saturn.mp4
│   ├── to-Uranus.mp4
│   ├── to-Neptune.mp4
│   ├── logo.svg
│   └── *.jpg
└── README.md
```

## Run locally

Serve the folder (do not open `index.html` as a `file://` URL, videos need HTTP):

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploy on GitHub Pages

1. Push this repository to GitHub.
2. Settings > Pages > Source: Deploy from a branch (`master` or `main` / `/root`).
3. Site URL: `https://<user>.github.io/planet-jumping/`

Asset paths must be **relative** (`assets/to-earth.mp4`), not absolute (`/assets/to-earth.mp4`).

Absolute paths work on localhost (root = `/`) but break on project Pages, because the browser requests `https://<user>.github.io/assets/...` instead of `https://<user>.github.io/planet-jumping/assets/...`.

## Controls

| Input | Action |
| --- | --- |
| Click portal / Space / Enter | Warp to next planet |
| Right / Down | Next planet |
| Left / Up | Previous planet |
| M | Mute / unmute |
| P | Eco mode |
| Esc | Close overlay |

## Data sources

Planetary metrics are curated from:

- NASA Planetary Fact Sheet (Goddard Space Flight Center)
- ESA Planetary Science Archive
- NASA JPL Horizons
