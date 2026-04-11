# Neon Typeracer

A neon-soaked 3D browser racing game where typing is the engine. Every correct letter nudges your car forward, every perfect word builds momentum, and every Nitro burst can turn a close race into a finish-line victory. Race against seven AI opponents across six futuristic tracks, earn Credits to unlock new cars and upgrades, and beat your own ghost lap to climb the leaderboard.

## What the game is

Neon Typeracer is a single-file HTML game built around a simple idea: typing faster and cleaner should make you drive faster. Instead of a traditional typing test, the game turns your accuracy and rhythm into a racing challenge. The player car moves along a procedural 3D track while seven AI racers hold the road beside you, each pacing themselves to the chosen difficulty.

Between races you spend the Credits you earn in the Garage, where four distinct cars and four upgrade paths let you push your performance further every session.

## Main features

- Fully playable in the browser with no installation required
- 3D racing presentation using Three.js
- Race against 7 AI opponents on the same track (8 cars total)
- 6 map environments with individual lap counts:
  - Circuit Zero (4 laps)
  - Redstone Ring (3 laps)
  - Orbital Loop (5 laps)
  - Summit Circuit (3 laps)
  - Seaside Sprint (4 laps)
  - Neon Abyss (2 laps)
- 3 difficulty modes: Easy, Medium, Hard
- Garage with 4 unlockable cars across four tiers (Starter, Sport, Hyper, Ultra)
- 4 upgrade tracks per car: Engine, Tires, Nitro Tank, Aero
- Credits economy — earn after every race, spend in the Garage
- Ghost car system — records your best lap per map and races it against you
- Drift Flow mechanic — consistent typing rhythm builds a flow meter that rewards Nitro and drift points
- Flow State banner on full drift meter
- Real-time HUD: speed, rank, WPM, Nitro, multiplier, combo, lap and checkpoint progress
- Analog speedometer and minimap
- Perfect-word combo system that rewards clean typing
- Multiplier cap scales with difficulty (Easy: x3.0, Medium: x2.5, Hard: x2.0 base, all raised further by the Aero upgrade)
- Nitro boosts earned through performance, checkpoints, and drift
- Procedural audio engine: 124 BPM in-race music, engine tone, and SFX
- Finish screen with rank, WPM, drift score, and credits breakdown
- Persistent save via localStorage (credits, upgrades, owned cars, ghost data)
- Neon arcade UI with dynamic visuals and speed-line effects
- Responsive layout for desktop and mobile browsers

## Core gameplay loop

1. Pick a track from the main menu under **RACE**.
2. Select a difficulty level.
3. Start the race.
4. Type the word shown in the center panel.
5. Press **Space** to submit the word.
6. Correct typing increases speed and builds your combo.
7. Keep your streak alive to raise your multiplier and earn Nitro.
8. Type with consistent rhythm to build **Drift Flow** — a full meter earns extra Nitro and drift points.
9. Press **Tab** to unleash a Nitro burst at the right moment.
10. Reach checkpoints for extra Nitro and a speed boost.
11. Beat the AI to the finish line.
12. Collect Credits, then visit the **Garage** to upgrade your car or buy a new one.

## Controls

### Desktop

- `Space` — submit the current word
- `Tab` — activate Nitro
- `Escape` — exit race and return to menu
- Click anywhere on the page to keep the hidden typing field focused

### Mobile

- Use the device keyboard to type
- Tap the screen to keep focus active
- The interface is designed to remain usable on smaller screens

## HUD and on-screen information

The top HUD keeps the race readable at a glance:

- **Position** shows your current rank among all 8 racers
- **WPM** reflects how quickly you are typing
- **Lap** shows current lap out of the map's total
- **Combo** shows your current perfect-word streak
- **Multiplier** reflects the current perfect-streak bonus
- **Checkpoint** shows progress within the current lap
- **Nitro dots** at the center show available boost charges

The lower typing panel shows the current word, a race progress bar, checkpoint status, combo count, the Drift Flow bar with running drift points, and a Nitro-ready hint when boost is available.

The speedometer on the lower-left shows your current speed in KM/H. The minimap on the lower-right shows your position, AI positions, the ghost car, and checkpoint markers.

## Maps

### Circuit Zero
A neon megacity oval with a tight chicane. Glowing towers, cyberpunk barriers, and vivid neon color define the most iconic Neon Typeracer look. **4 laps.**

### Redstone Ring
A dusty alien canyon loop with elevation changes. Jagged rock formations line the course under harsh orange lighting, like racing through a hostile outpost under pressure. **3 laps.**

### Orbital Loop
A zero-g ring station superhighway. Stars fill the background, glowing ring structures float overhead, and the lighting is cool and cosmic. The fastest-feeling map visually. **5 laps.**

### Summit Circuit
A mountain hairpin loop with switchbacks and dramatic elevation changes. Rocky outcroppings frame the road and the atmosphere is cold and exposed. **3 laps.**

### Seaside Sprint
Ocean-side sweeping curves with open sky and coastal panorama. A more open, flowing layout compared to the tighter urban and underground maps. **4 laps.**

### Neon Abyss
An underground neon tunnel circuit lit by vivid floor glow and barrier strips. The narrowest track in the game — concentrated pressure from start to finish. **2 laps.**

Each map changes the visuals, track layout, ambient lighting, fog density, road width, and roadside scenery while keeping the same racing rules.

## Difficulty settings

### Easy
Best for learning the game and getting comfortable with the typing-to-speed rhythm. Higher word boost, more Nitro from clean typing, and a higher multiplier cap (x3.0 base). AI racers are relaxed and forgiving.

### Medium
A balanced challenge that gives the race a good competitive pace. Moderate boost values and a multiplier cap of x2.5 base.

### Hard
Designed for players who want constant pressure and tight competition. Lower word boost, less Nitro gain, and a tighter multiplier cap (x2.0 base). AI racers are fast and unrelenting.

Difficulty adjusts the player's speed gains, Nitro rewards, multiplier ceiling, and AI pace, so the race feels meaningfully different at each level.

## The Garage

The Garage lets you buy cars and purchase upgrades using Credits earned from races.

### Cars

| Car | Class | Price | Description |
|---|---|---|---|
| Apex Type-01 | Starter | Free | Balanced starter. Master the fundamentals. |
| Phantom GT | Sport | 800 CR | Precision-engineered for corner mastery. |
| Nova Storm | Hyper | 2,200 CR | Raw speed. High risk, higher reward. |
| Titan Apex | Ultra | 5,000 CR | The absolute pinnacle. Unstoppable force. |

Each car has its own speed, acceleration, handling, and nitro stats visible in the Garage. Cars are previewed in a 3D rotating display with full neon lighting.

### Upgrades

Upgrades apply globally across all owned cars and have four levels each:

- **Engine** — increases the speed gain from each correct keystroke
- **Tires** — reduces speed decay between keystrokes
- **Nitro Tank** — increases maximum Nitro charge capacity (3 → 5 charges)
- **Aero** — raises the multiplier cap above the difficulty base (up to +0.8 additional)

## Scoring and progression systems

### Speed from typing
Typing the target word correctly pushes your car forward letter by letter. Each correct keystroke adds speed. Mistakes slow you down and reset your combo.

### Combo and Multiplier
Consecutive perfect words raise your combo counter and your multiplier. A higher multiplier makes every correct keystroke produce more speed and earns Nitro faster. Multiplier resets on any mistake. The cap depends on difficulty and your Aero upgrade level.

### Drift Flow
Typing with consistent rhythm — steady intervals between keystrokes — builds the Drift Flow meter. A full meter triggers a **Flow State** event, granting Nitro, drift smoke particles, and ongoing drift points. Drift points are tallied on the finish screen.

### Nitro
Nitro is the game's active boost resource. You earn charges by typing perfectly, hitting checkpoints, and maxing the Drift Flow meter. Press `Tab` to burn a charge for a large speed burst.

### Checkpoints
Each lap is divided into five checkpoint segments. Crossing each one rewards extra Nitro and a speed boost, keeping the pace of the race dynamic throughout.

### Credits
After each race you earn Credits based on four factors: finish position, WPM, perfect word count, and max combo. Credits are saved persistently and spent in the Garage.

### Ghost system
After each race your run is saved as a ghost for that map if it was your fastest. On future runs the ghost car appears on the track and the HUD shows whether you are ahead or behind in real time.

## Game screens

### Menu screen
Two options: **Race** (map and difficulty select) and **Garage** (cars and upgrades). Your current Credits balance is shown at the bottom.

### Map Select
Displays all six circuits as cards with a minimap preview, biome label, and lap count. Difficulty is chosen here before starting.

### Countdown
A short 3-2-1 countdown before the race begins.

### Race screen
Shows the live 3D race, the typing prompt, the analog speedometer, the minimap, AI positions, and all gameplay stats.

### Finish screen
Displays final rank, WPM, drift score, selected map, difficulty, lap count, credits breakdown, and ghost status (new record or defended).

## Project structure

This project is intentionally simple and portable:

- One HTML file for the game logic, interface, and visuals
- No build step
- No external installation or launcher needed
- Easy to share, modify, or embed

## Running locally

Open `neon_typeracer.html` in a modern browser.

## Roadmap ideas

- More maps and visual themes
- Additional word sets and challenge modes
- Audio music polish with more layered feedback
- Online leaderboards or shared ghost races
- Accessibility options for typing assistance and visual clarity

## License

MIT License
