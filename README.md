# Unnamed Talking Club

A Jeopardy-style challenge board for Improv / Toastmasters club gatherings. Participants pick a category and difficulty level (1-5) to receive a situation they must perform, present, or narrate on the spot.

## Quick start

```bash
npx serve .
```

Open `http://localhost:3000` in your browser.

## How it works

- The board shows **categories** as columns and **difficulty levels** 1-5 as rows
- Click a cell to reveal the challenge in a full-screen overlay
- A built-in **countdown timer** (default 3 min, adjustable 1-10 min) lets the actor and audience track time
- Opened cards are dimmed to track progress (resets on page reload)

## Editing questions

All challenges live in `questions.txt`. The format is:

```
[Category Name]
1: Easy situation text
2: Slightly harder situation
3: Moderate challenge
4: Difficult scenario
5: Most complex challenge

[Another Category]
1: ...
```

- Categories are declared with square brackets: `[Name]`
- Each line starts with the level number and a colon: `N: text`
- Blank lines between categories are ignored
- The board grid adapts automatically to the number of categories

## Features

- Single HTML file with all CSS and JS inline — no build step
- No external dependencies — fully offline-capable
- Microsoft Fluent Design color palette
- Smooth CSS animations for card reveal / close
- Timer with warning (amber at 30s) and expired (pulsing red at 0:00) states
- Keyboard support: Escape to close overlay

## Tech

| | |
|---|---|
| Runtime | Any static file server + modern browser |
| Dependencies | None |
| Files | `index.html`, `questions.txt` |
| Colors | `#0078d4` (blue), `#50e6ff` (cyan), `#1b1b1b` (background) |
| Font | Segoe UI / Cascadia Code (timer) |
