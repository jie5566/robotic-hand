# Robotic Hand · Live Gesture Mirror

A photoreal robotic hand in the browser that mirrors your real hand through your webcam.

**▶ Try it: https://jie5566.github.io/robotic-hand/**

Click **Start camera**, allow camera access, and hold your hand up — the robot hand copies your wrist orientation, every finger joint, your thumb, and where your hand is on screen. Without a camera it plays an idle demo pose.

## Features

- **Full hand tracking** — wrist rotation, 3 joints per finger, finger spread, thumb, position and distance, via [MediaPipe Hand Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker)
- **Procedural model** — every part is generated in code with [three.js](https://threejs.org): smooth superellipse shells, lathe-turned joint caps, machined spur gears
- **Studio look** — lacquered satin paint, glossy black chrome, HDR softbox environment, ambient occlusion
- **Real gear train** — the wrist gears are a properly meshed pair (same module, correct centre distance, 16:11 ratio) and only turn when your wrist bends or your fingers curl
- **Single file** — everything lives in `index.html`; no build step, no install

## Controls

| Control | What it does |
| --- | --- |
| Start / Stop camera | Turns webcam tracking on or off |
| Follow position | When on, the robot hand moves around the screen with your hand |
| Swap left / right | Use it if the palm and back of the hand appear swapped |
| Reset view | Puts the camera back after you've orbited |
| Drag / scroll | Orbit around and zoom |

## Run it locally

Open `index.html` in Chrome, Edge or Safari. You need an internet connection the first time, because three.js and the tracking model load from public CDNs.

Camera access only works on `https://` pages or on `localhost`. If your browser blocks it when opening the file directly, serve the folder instead:

```bash
npx serve .
# or
python3 -m http.server
```

## Privacy

Video never leaves your device. Hand tracking runs entirely in your browser; nothing is uploaded or recorded.

## Built with

- [three.js](https://threejs.org) — rendering, post-processing (GTAO)
- [MediaPipe Tasks Vision](https://www.npmjs.com/package/@mediapipe/tasks-vision) — hand landmark detection
