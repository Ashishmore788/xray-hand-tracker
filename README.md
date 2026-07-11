# 🖐️ X-Ray Hand Tracker

A browser-based hand tracker that renders a gesture-controlled visual effects window over your webcam feed. Pinch your thumb and index finger together to switch between a glowing **particle** effect and a medical-imaging style **X-ray** effect — all running client-side, no server or build step required.

![status](https://img.shields.io/badge/status-experimental-orange)
![license](https://img.shields.io/badge/license-MIT-blue)

## ✨ Features

- **Real-time hand tracking** via [MediaPipe Tasks Vision](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) (21-point landmark model, GPU-accelerated)
- **Gesture-controlled mode switching** — pinch (thumb tip + index tip) to trigger X-ray mode, release to return to particle mode
- **Custom GLSL shaders** rendered with [Three.js](https://threejs.org/), including:
  - Particle mode: animated contour lines, an 90x90-cell strobing particle grid with color cycling, and subject glow
  - X-ray mode: brightness-mapped blue tones, Sobel edge detection, film grain, and scanlines
- **Works with one or two hands** — single-hand pinch uses your hand's bounding box as the effect window; two-hand pinch creates a strip between both hands
- **Live hand skeleton overlay** drawn on a 2D canvas
- Fully responsive, maintains correct video aspect ratio at any window size
- Zero build tooling — it's a single static HTML file

## 🚀 Demo

Open `index.html` directly in a modern desktop browser (Chrome recommended) and grant camera access. See [Deployment](#-deployment-github-pages) below to host it live.

## 🧰 Tech Stack

| Purpose | Library | Loaded via |
|---|---|---|
| Hand landmark detection | `@mediapipe/tasks-vision` | jsDelivr CDN (ES module) |
| 3D / shader rendering | `three` | jsDelivr CDN (ES module) |
| Everything else | Vanilla JavaScript, HTML, CSS | — |

No `npm install`, no bundler, no framework — the whole app is one HTML file that imports its dependencies directly from a CDN as ES modules.

## 📦 Getting Started

### Run locally

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/xray-hand-tracker.git
   cd xray-hand-tracker
   ```
2. Serve the folder with any static file server (camera access requires `http://localhost` or `https://`, so you generally can't just double-click the file — some browsers are stricter than others about `file://`):
   ```bash
   # Python
   python3 -m http.server 8000

   # or Node
   npx serve .
   ```
3. Open `http://localhost:8000` in your browser and allow camera access.

### Usage

1. Wait for **"Loading AI Models & Camera…"** to disappear.
2. Hold up one or both hands in frame.
3. **Pinch** your thumb and index finger tip together to trigger **X-ray mode**.
4. Release the pinch (or spread your hand open) to return to **particle mode**.
5. With two hands, spread them apart to control the size/position of the particle effect window; pinch both simultaneously for a two-hand X-ray strip.

## 🌐 Deployment (GitHub Pages)

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, choose your default branch and the `/ (root)` folder.
4. Save. Your app will be live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

GitHub Pages serves over HTTPS by default, so camera access will work without any extra configuration.

## ⚠️ Requirements & Browser Support

- A webcam
- A modern desktop browser with support for:
  - `getUserMedia` (camera access)
  - WebGL (for Three.js rendering)
  - WebAssembly (for the MediaPipe runtime)
  - ES module `<script type="module">` imports
- **HTTPS or `localhost`** — browsers block camera access on plain `http://` origins other than localhost
- Chrome (desktop) is the most reliably tested browser. Safari and Firefox should mostly work but haven't been extensively tested.

## 🐛 Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| Stuck on "Loading AI Models & Camera…" | Camera permission denied, or no camera found | Check browser permission settings; test the camera in another app |
| Black screen, no shader effect | WebGL unsupported/disabled | Test at [get.webgl.org](https://get.webgl.org); try a different browser |
| No hand skeleton appears | Poor lighting, hand out of frame, or model still loading | Improve lighting, move hand fully into frame, wait a few seconds |
| Pinch doesn't trigger X-ray mode | Pinch threshold not met | Bring thumb and index fingertip closer together — try tapping them fully together |
| Fetch/network errors in a hosted preview sandbox (e.g. CodeSandbox, Claude Artifacts) | Sandbox CSP blocks the CDN domains this app fetches from (`cdn.jsdelivr.net`, `storage.googleapis.com`) | Run it as a normal hosted page (GitHub Pages, `localhost`, etc.) — this isn't a bug in the app itself |

## 📁 Project Structure

```
xray-hand-tracker/
├── index.html      # entire app: markup, styles, and JS in one file
├── README.md
└── LICENSE
```

## 🗺️ Roadmap / Ideas

- [ ] Record video with effects applied
- [ ] Additional shader presets (thermal, blueprint, night-vision)
- [ ] More gestures (peace sign, thumbs up, fist)
- [ ] On-screen FPS counter
- [ ] Mobile/touch support

Contributions and forks welcome — open an issue or PR.

## 📄 License

MIT — see [LICENSE](LICENSE).
