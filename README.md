# 🏎️ Neon Typeracer — Electron Desktop App

A 3D neon-styled typing racing game built with Electron. Type words to accelerate your car, chain combos to build a multiplier, hit nitro boosts, and race AI opponents across six unique circuits — all from your desktop. No internet required after install.

---

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Getting Started](#getting-started)
3. [Building a Distributable](#building-a-distributable)
4. [Gameplay Guide](#gameplay-guide)
5. [Circuits](#circuits)
6. [Garage & Cars](#garage--cars)
7. [Difficulty Modes](#difficulty-modes)
8. [HUD Reference](#hud-reference)
9. [Project Structure](#project-structure)
10. [Tech Stack](#tech-stack)
11. [Troubleshooting](#troubleshooting)
12. [License](#license)

---

## Prerequisites

- **Node.js 18+** — install via [nvm](https://github.com/nvm-sh/nvm) (recommended) or your system package manager:
  ```bash
  sudo apt install nodejs npm   # Debian/Ubuntu
  brew install node             # macOS (Homebrew)
  ```
- **npm** (bundled with Node.js)

---

## Getting Started

```bash
# 1. Install dependencies
npm install

# 2. Launch in development mode  
npm start
```

The game window opens at 1280×720 (minimum 960×540). The menu bar is hidden by default; press `F11` to toggle fullscreen.

---

## Building a Distributable

Build for **your current OS only** — cross-compilation is not supported for Electron apps.

| OS      | Command               | Output in `dist/`                                        |
|---------|-----------------------|----------------------------------------------------------|
| Linux   | `npm run build:linux` | `Neon Typeracer-1.0.0.AppImage` + `.deb`                 |
| Windows | `npm run build:win`   | `.exe` NSIS installer + portable `.exe`                  |
| macOS   | `npm run build:mac`   | `.dmg`                                                   |

> **Note:** The Windows build config uses NSIS with `oneClick: false`, so the installer lets users choose the install directory.

### Running the Linux AppImage

```bash
chmod +x "dist/Neon Typeracer-1.0.0.AppImage"
./"dist/Neon Typeracer-1.0.0.AppImage"
```

### Installing the Debian package

```bash
sudo dpkg -i dist/neon-typeracer_1.0.0_amd64.deb
```

---

## Gameplay Guide

### Core Loop

1. **Select a circuit** from the Map Select screen and choose a difficulty.
2. **Type the word** displayed in the Typing Panel at the bottom of the screen.
3. **Press `SPACE`** to submit a completed word — this boosts your car's speed.
4. **Build a combo** by submitting words in a row without mistakes. Each consecutive correct word increases your multiplier (up to 3× on Easy, 2× on Hard).
5. **Drift Flow bar** fills as you maintain a combo. When it's full, a bonus is awarded.
6. **Press `TAB`** to fire a Nitro boost when the Nitro badge lights up. Nitros are earned by perfect words and checkpoint crossings.
7. **Race 7 AI opponents** to the finish. The AI uses rubber-banding — difficulty controls how aggressively they catch up.

### Scoring

- Each submitted word earns points scaled by your current multiplier.
- Combos increase the multiplier incrementally.
- Breaking a combo (typo or partial submission) resets the combo to zero.
- Drift Flow bonus points are awarded when the bar fills completely.
- Final credits (in-game currency) are calculated from position, combo performance, and race time.

---

## Controls

| Key      | Action                                              |
|----------|-----------------------------------------------------|
| Type     | Enter characters for the current word               |
| `SPACE`  | Submit the current word and boost speed             |
| `TAB`    | Fire Nitro boost (when Nitro badge is active)       |
| `ESC`    | Quit the current race and return to menu            |
| `F11`    | Toggle fullscreen                                   |

---

## Circuits

The game features six hand-crafted closed-loop circuits, each with distinct geometry, colour palette, and atmosphere:

| Circuit         | Biome        | Laps | Description                                  |
|-----------------|--------------|------|----------------------------------------------|
| Circuit Zero    | Cyberpunk    | 4    | Neon megacity oval with tight chicane        |
| Redstone Ring   | Alien        | 3    | Dusty canyon loop with elevation changes     |
| Orbital Loop    | Cosmic       | 5    | Zero-g ring station superhighway            |
| Summit Circuit  | Alpine       | 3    | Mountain hairpin loop with switchbacks       |
| Seaside Sprint  | Coastal      | 4    | Coastal sweeper with ocean views             |
| Neon Abyss      | Underground  | 2    | Tight underground neon tunnel circuit        |

Every circuit has 5 checkpoints per lap. Crossing a checkpoint rewards a partial Nitro charge.

---

## Garage & Cars

Earn credits by finishing races, then spend them in the Garage to unlock new cars or upgrade your existing one.

### Cars

| Car            | Class   | Price  | Strengths               |
|----------------|---------|--------|-------------------------|
| Apex Type-01   | Starter | Free   | Balanced all-rounder    |
| Phantom GT     | Sport   | 800 CR | Exceptional handling    |
| Nova Storm     | Hyper   | 2200 CR| Raw top speed + Nitro   |
| Titan Apex     | Ultra   | 5000 CR| Elite across all stats  |

### Upgrades

Each car has four upgradeable systems, each with five levels (Level 0 is stock):

| Upgrade    | Effect                                 | Max Cost (all levels) |
|------------|----------------------------------------|-----------------------|
| Engine     | Increases speed multiplier             | 1100 CR               |
| Tires      | Tightens cornering & handling          | 1200 CR               |
| Nitro Tank | Increases max stored Nitro charges     | 880 CR                |
| Aero       | Improves high-speed stability          | 1500 CR               |

---

## Difficulty Modes

Difficulty affects AI speed, rubber-banding, Nitro earn rate, multiplier cap, and how hard typos brake you:

| Setting | AI Base Speed | Multiplier Cap | Rubber-Band | Typo Brake |
|---------|--------------|----------------|-------------|------------|
| Easy    | 35–80        | 3.0×           | Strong      | Mild       |
| Medium  | 55–118       | 2.5×           | Moderate    | Moderate   |
| Hard    | 90–168       | 2.0×           | Weak        | Severe     |

On Hard, the AI runs at up to 168 units of speed with a 1.5% chance of spontaneous burst acceleration per tick, making consistent typing the only way to keep pace.

---

## HUD Reference

The in-race HUD is split into five zones:

**Top-left — Position Panel**
Shows your current race position (e.g. `P1`), total racers, and your driver label.

**Top-center — Race Info**
Displays the circuit name, current lap out of total, and checkpoint progress.

**Top-center (below) — Nitro Dots**
A row of dots showing how many Nitro charges you have stored. Lit dots are ready to fire with `TAB`.

**Top-right — Racing Metrics**
Live WPM (words per minute), current Combo streak, and current score multiplier.

**Bottom — Typing Panel**
The word to type, a progress bar showing race completion, checkpoint counter, Combo counter, and the Drift Flow bar. The Nitro badge appears here when a Nitro is ready.

**Minimap** (bottom-right, hidden on screens < 1000px wide)
A top-down 154×154px canvas showing all car positions on the circuit.

---

## Project Structure

```
neon-typeracer-electron/
├── main.js          # Electron main process
│                    #   Window creation (1280×720, min 960×540)
│                    #   GPU flags for Linux compatibility
│                    #   F11 fullscreen handler
│                    #   IPC bridge setup
│
├── preload.js       # Secure context bridge
│                    #   Exposes `window.electronAPI.platform` and
│                    #   `window.electronAPI.isElectron` to the renderer
│
├── index.html       # Entire game — self-contained HTML/CSS/JS
│                    #   Six circuit definitions
│                    #   Car and upgrade data
│                    #   Three.js 3D scene rendering
│                    #   Web Audio API music & SFX engine
│                    #   Typing engine, combo/scoring logic
│                    #   AI racer simulation (7 opponents)
│                    #   Garage, map select, finish screen UIs
│
├── icon.png         # Application icon (used by electron-builder)
├── package.json     # Build configuration and npm scripts
└── README.md
```

---

## Tech Stack

| Layer        | Technology                        | Version  |
|--------------|-----------------------------------|----------|
| Desktop shell| [Electron](https://electronjs.org)| v33      |
| Build tooling| [electron-builder](https://www.electron.build) | v25 |
| 3D rendering | [Three.js](https://threejs.org)   | r128     |
| Audio        | Web Audio API (no library)        | —        |
| UI / Logic   | Vanilla JS + HTML5 Canvas         | —        |

All game logic, rendering, audio synthesis, and UI live in a single `index.html` file — no bundler, no framework, no build step for development.

The Web Audio API engine synthesises a procedural drum-and-bass soundtrack at 124 BPM using oscillators, noise buffers, and gain envelopes entirely at runtime. Engine sound pitch is mapped live to your car's current speed.

---

## Troubleshooting

| Symptom                           | Likely Cause                        | Fix                                                      |
|-----------------------------------|-------------------------------------|----------------------------------------------------------|
| Black / blank window              | GPU driver issue                    | Launch with `--disable-gpu`                              |
| "SUID sandbox helper" error       | Linux sandbox restriction           | Already handled in `main.js`; if it persists, add `--no-sandbox` |
| No audio on first launch          | Browser autoplay policy             | Click anywhere in the window to unlock the Audio Context |
| `electron` command not found      | Dependencies not installed          | Run `npm install` first                                  |
| Build fails with "wrong OS" error | Cross-compile attempt               | Run only the build script that matches your OS           |
| Window too small / clipped        | Display scaling                     | Minimum supported size is 960×540; garage and minimap hide automatically below 1000px wide |
| Game runs but feels slow          | Software rendering fallback         | Ensure GPU drivers are up to date; try with `--ignore-gpu-blocklist` (already in `main.js`) |

### Linux-Specific AppImage Notes

If the AppImage fails to launch with a sandbox error even with `--no-sandbox`:

```bash
./"dist/Neon Typeracer-1.0.0.AppImage" --no-sandbox --disable-gpu-sandbox
```

Both flags are already set in `main.js` for the dev environment, but AppImage packaging may strip command-line arguments.

---

## License

MIT
