# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file web project — all HTML, CSS, and JavaScript lives in `tictactoe.html`. There is no build step, no package manager, and no dependencies.

## Running the Project

Open `tictactoe.html` directly in a browser:

```bash
start tictactoe.html        # Windows
open tictactoe.html         # macOS
xdg-open tictactoe.html     # Linux
```

## Architecture

Everything is contained in `tictactoe.html`:

- **HTML** — 3×3 grid of `.cell` divs, status text, score display, and two control buttons
- **CSS** — dark theme (`#1a1a2e` background), grid layout, hover/win animations
- **JS** — game logic at the bottom of the file in a `<script>` tag

Key JS state:
- `board` — 9-element array of `''`, `'X'`, or `'O'`
- `current` — whose turn it is (`'X'` or `'O'`)
- `vsAI` — boolean toggling 2-player vs AI mode
- `scores` — `{ X, O, D }` persisted across games within the session

The AI (`bestMove`) uses simple priority: win > block > center > corner > random. It does not use minimax.

## Git Workflow

After every meaningful change:
1. Stage the changed file(s) by name
2. Commit locally with a clean, descriptive message
3. Push to GitHub (`git push origin master`)
