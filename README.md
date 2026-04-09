# Neon Typeracer

A neon-soaked 3D browser racing game where typing is the engine. Every correct letter nudges your car forward, every perfect word builds momentum, and every Nitro burst can turn a close race into a finish-line victory. Race against three AI opponents across futuristic tracks, survive the pressure of fast-moving checkpoints, and finish first in a game that blends typing skill with arcade racing energy.

## What the game is

Neon Typeracer is a single-file HTML game built around a simple idea: typing faster and cleaner should make you drive faster. Instead of a traditional typing test, the game turns your accuracy and rhythm into a racing challenge. The player car moves along a procedural 3D track while three AI racers stay on the road beside you, each with their own pace depending on the chosen difficulty.

The result is a quick, replayable arcade loop that is easy to understand at first glance and rewarding to master over time.

## Main features

- Fully playable in the browser with no installation required
- 3D racing presentation using Three.js
- Race against 3 AI opponents on the same track
- 3 map environments:
  - The Grid
  - Mars Outpost
  - Starlight
- 3 difficulty modes:
  - Easy
  - Medium
  - Hard
- Real-time stats for speed, rank, WPM, Nitro, multiplier, combo, and checkpoint progress
- Perfect-word combo system that rewards clean typing
- Multiplier growth up to x2.5
- Nitro boosts earned through performance and checkpoints
- Finish screen with rank and final stats
- Neon arcade UI with dynamic visuals
- Responsive layout for desktop and mobile browsers

## Core gameplay loop

1. Pick a track theme from the main menu.
2. Select a difficulty level.
3. Start the race with **IGNITION**.
4. Type the word shown in the center panel.
5. Press **Space** to submit the word.
6. Correct typing increases speed and helps build your combo.
7. Keep your streak alive to raise your multiplier and earn Nitro.
8. Press **Tab** to unleash Nitro at the right moment.
9. Reach checkpoints for extra rewards.
10. Beat the AI to the finish line.

## Controls

### Desktop

- `Space` — submit the current word
- `Tab` — activate Nitro
- Click anywhere on the page to keep the hidden typing field focused

### Mobile

- Use the device keyboard to type
- Tap the screen to keep focus active
- The interface is designed to remain usable on smaller screens

## HUD and on-screen information

The top HUD keeps the race readable at a glance:

- **Velocity** shows the current speed of your car
- **Rank** shows your current position in the race
- **WPM** reflects how quickly you are typing
- **Nitro** shows available boost charges
- **Multiplier** reflects the current perfect-streak bonus
- **Track** displays a small minimap view of the race progress

The lower typing panel shows the current word, a progress bar, checkpoint status, combo count, and a Nitro-ready hint when boost is available.

## Maps

### The Grid
A neon city track with a cyberpunk look. It uses glowing tones, futuristic roadside structures, and overhead elements that make the race feel like it is happening through a digital metropolis.

### Mars Outpost
A rugged red-surface course with canyon-like scenery and dusty ambient details. It feels heavier and more grounded, with a more industrial sci-fi vibe.

### Starlight
A deep-space route with stars, floating sci-fi accents, and a cool high-speed atmosphere. It is the most cosmic-looking of the three environments.

Each map changes the visuals, track styling, ambient lighting, and roadside scenery while keeping the same racing rules.

## Difficulty settings

### Easy
Best for learning the game and getting comfortable with the typing-to-speed rhythm.

### Medium
A balanced challenge that gives the race a good competitive pace.

### Hard
Designed for players who want constant pressure and tighter competition from the AI.

Difficulty changes AI speed and handling behavior, so the race feels different depending on the mode you choose.

## Scoring and progression systems

### Speed from typing
Typing the target word correctly pushes your car forward. Correct letters help build momentum, while mistakes slow you down.

### Combo system
Consecutive perfect words raise your combo counter. The combo is not just cosmetic; it contributes to your multiplier and encourages accurate, streak-based play.

### Multiplier
Your multiplier grows as you maintain a strong streak, up to x2.5. A higher multiplier makes good typing more rewarding and helps you recover race position more quickly.

### Nitro
Nitro is the game’s active boost resource. You earn it by playing well and by hitting checkpoints. Once you have at least one charge, you can press `Tab` to burst forward.

### Checkpoints
The track is divided into checkpoint segments. Crossing a checkpoint rewards you with progress feedback and extra Nitro, which creates a nice mid-race push and prevents the race from feeling flat.

## Game screens

### Menu screen
Lets you choose the map and difficulty before starting.

### Countdown
A short start countdown appears before the race begins.

### Race screen
Shows the live race, your typing prompt, the minimap, the AI positions, and all gameplay stats.

### Finish screen
Displays the final result, rank, WPM, selected map, and number of perfect words.

## Project structure

This project is intentionally simple and portable:

- One HTML file for the game logic, interface, and visuals
- No build step
- No external installation or launcher needed
- Easy to share, modify, or embed

## Running locally

Open `neon_typeracer.html` in a modern browser.

## Why this format works well

The game is designed for short sessions with immediate feedback. You can start a race in seconds, but there is enough depth in the combo, multiplier, checkpoint, and Nitro systems to keep repeated runs interesting.

That makes it a good fit for browser play, small game jams, and itch.io-style releases where quick access matters.

## Roadmap ideas

- Persistent high scores saved across sessions
- More maps and visual themes
- Additional word sets or challenge modes
- Audio/music polish with more feedback layers
- Leaderboards or ghost races
- Accessibility options for typing assistance and visual clarity

## License

MIT License
