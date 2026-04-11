# Neon Typeracer — Electron Desktop App

## Prerequisites

- Node.js 18+ (`sudo apt install nodejs npm` or via nvm)

## Build & Run

```bash
# 1. Install dependencies
npm install

# 2. Run in dev mode
npm start

# 3. Build for YOUR platform (Linux in your case)
npm run build:linux
```

The built app will be in `dist/`:
- **AppImage**: `dist/Neon Typeracer-1.0.0.AppImage` (portable, run directly)
- **deb**: `dist/neon-typeracer_1.0.0_amd64.deb` (install with `sudo dpkg -i`)

### Running the AppImage
```bash
chmod +x "dist/Neon Typeracer-1.0.0.AppImage"
./"dist/Neon Typeracer-1.0.0.AppImage"
```

## IMPORTANT: Build for YOUR OS

You're on Linux (Debian) — use `npm run build:linux`, NOT `build:win`.
Windows builds only work on Windows. Cross-compilation via Wine will NOT work for Electron apps.

| Your OS   | Command              | Output                    |
|-----------|----------------------|---------------------------|
| Linux     | `npm run build:linux`| AppImage + .deb           |
| Windows   | `npm run build:win`  | .exe installer + portable |
| macOS     | `npm run build:mac`  | .dmg                      |

## Controls

- **Type words** → accelerate
- **SPACE** → submit word
- **TAB** → nitro boost
- **ESC** → quit race
- **F11** → fullscreen

## Troubleshooting

- **Black screen**: Run with `--disable-gpu` flag: `./app --disable-gpu`
- **Sandbox errors on Linux**: Already handled in main.js, but if needed: `./app --no-sandbox`
