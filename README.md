# 🏎️ Neon Typeracer — Electron Desktop App

A 3D neon-styled typing racing game built with Electron. Type words to accelerate, hit nitro boosts, and race to the finish line — all from your desktop.

---

## Prerequisites

- **Node.js 18+** — install via [nvm](https://github.com/nvm-sh/nvm) (recommended) or your package manager:
  ```bash
  sudo apt install nodejs npm   # Debian/Ubuntu
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

---

## Building a Distributable

Build for **your current OS only** — cross-compilation is not supported for Electron apps.

| OS      | Command               | Output in `dist/`                        |
|---------|-----------------------|------------------------------------------|
| Linux   | `npm run build:linux` | `Neon Typeracer-1.0.0.AppImage` + `.deb` |
| Windows | `npm run build:win`   | `.exe` installer + portable `.exe`       |
| macOS   | `npm run build:mac`   | `.dmg`                                   |

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

## Controls

| Key       | Action              |
|-----------|---------------------|
| **Type**  | Accelerate your car |
| `SPACE`   | Submit current word |
| `TAB`     | Nitro boost         |
| `ESC`     | Quit the race       |
| `F11`     | Toggle fullscreen   |

---

## Project Structure

```
neon-typeracer-electron/
├── main.js        # Electron main process — window setup & IPC
├── preload.js     # Preload script — secure renderer bridge
├── index.html     # Game UI & logic (self-contained)
├── icon.png       # App icon
├── package.json   # Build config & scripts
└── README.md
```

---

## Troubleshooting

| Symptom                       | Fix                                                       |
|-------------------------------|-----------------------------------------------------------|
| Black / blank screen          | Launch with `--disable-gpu` flag                          |
| Sandbox errors on Linux       | Launch with `--no-sandbox` (already handled in `main.js`) |
| `electron` not found          | Run `npm install` first                                   |
| Build fails on wrong OS       | Use the build command matching your current OS (see table above) |

**Tip:** If you're on Linux and see a "SUID sandbox helper" error, try:
```bash
./"dist/Neon Typeracer-1.0.0.AppImage" --no-sandbox
```

---

## Tech Stack

- [Electron](https://www.electronjs.org/) v33
- [electron-builder](https://www.electron.build/) v25
- Vanilla JS / HTML5 Canvas (no frontend framework)

---

## License

MIT
