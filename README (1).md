# Coin Collector

A small 3D browser game built for the VI3W game developer challenge. Collect gold coins, dodge the red spikes, and see how high you can score.

**Play it:** https://claude.ai/artifact/9rPgBseStCcnKCgJ6BxJoP

## What came from VI3W

All three 3D assets were sketched by hand and generated with [VI3W](https://app.vi3w.in) (Sketch → Image → 3D, Trellis model), then exported as GLB:

| Asset | File |
| --- | --- |
| Gold star coin | `assets/coin.glb` |
| Red spike obstacle | `assets/spike.glb` |
| Blue player character | `assets/player.glb` |

## How the game works

- Move with **WASD** or the **arrow keys**. On a phone, use the on-screen pad.
- Each coin is worth 10 points. Obstacles speed up as your score rises.
- You have 3 lives. A hit gives you a short blink of invulnerability.
- Game over shows your score, with a button to play again.

## Tech

- JavaScript with [Three.js](https://threejs.org) r128 and `GLTFLoader`
- Everything is in one file, `index.html`
- The three GLB models are embedded in the file as base64, so it opens with no setup

## Code overview

`index.html` contains, in order:

1. **Scene setup**: camera, lights, shadows, ground and decorative trees
2. **Player, coin and spike builders**: simple placeholder shapes, replaced by the VI3W models after they load
3. **Game state**: score, lives, start, game over and restart
4. **Input**: keyboard and touch pad
5. **Model loading**: parses each GLB, centres it, scales it to game size and adjusts its material so it shows up with the game's lighting
6. **Game loop**: movement, coin pickup, obstacle movement, collision and camera follow
7. **Embedded models**: base64 data at the bottom of the file, loaded automatically on start

## Run it locally

1. Download `index.html`.
2. Open it in a browser. No install or server is needed (it loads Three.js from a CDN, so you need an internet connection).

## Swap in your own models

The three loader buttons are hidden by default. To use different models, remove `.file,` from the CSS rule that hides them (`.file,#msg{display:none}`), then use the buttons on the start screen to load your own `.glb` files for the coin, spike and character.

## Built with

- [VI3W](https://app.vi3w.in) for the 3D assets
- [Claude](https://claude.ai) for help writing the code
