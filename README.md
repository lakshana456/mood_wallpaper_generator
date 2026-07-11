# Mood Wallpaper Generator

A living wallpaper you can drop into any browser. Pick a mood — chill, study, rainy, or energetic —
and get a unique looping animation with a matching generative ambient soundtrack, no external
audio or image files required.

## Features

- 4 distinct moods, each with its own color palette, particle system, and physics
  - **Chill** — slow-drifting soft-glow orbs in indigo and periwinkle
  - **Study** — warm amber dust motes drifting upward like lamplight
  - **Rainy** — falling rain streaks with occasional soft lightning flashes
  - **Energetic** — fast bouncing neon particles with a pulsing glow
- Procedurally generated ambient audio per mood using the Web Audio API (oscillators + filtered
  noise) — no MP3s, no licensing concerns, no network requests
- Smooth 60fps canvas animation, fully responsive down to mobile
- Sound toggle and mood switcher with no page reload — state transitions are instant
- Single dependency-free HTML file — works offline, easy to fork or extend

## How it works

- All rendering is done on an HTML5 `<canvas>` using `requestAnimationFrame`
- Each mood defines a particle factory (`makeParticle`) and a physics update step, so adding a
  new mood is just adding a new entry to the `moods` object plus a branch in `update`/`render`
- Audio is synthesized live in-browser: sine waves for chill's pad tones, filtered white noise
  for study's focus hum and rain's texture, and a gain-automated square wave for energetic's pulse

