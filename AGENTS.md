# AGENTS.md

## Repository Overview
- Zero-dependency, vanilla HTML5 Canvas + JavaScript (ES6+) Arcade game (Asteroids clone).
- No package manager (`package.json`), build system, bundler, linter, or automated test suite.

## Development & Execution
- **Run locally**: Open `index.html` directly in a web browser or serve static files using `npx serve .` (default port `3000`).
- **No Build Step**: Changes to `game.js` or `index.html` take effect immediately on browser refresh.

## Key Architecture Facts
- **`index.html`**: Entry point defining fixed `#canvas` element (`800x600`).
- **`game.js`**: Monolithic game script containing all logic (`'use strict'`), game loop (`requestAnimationFrame`), and state:
  - Global canvas dimensions: `W = 800`, `H = 600`.
  - Main entities: `Ship`, `Asteroid`, `Bullet`, `Particle`.
  - Game states: `'playing'`, `'dead'`, `'gameover'`.
- Script is included via plain `<script src="game.js"></script>` (no ES modules). Keep code compatible with direct browser inclusion without import/export statements.
