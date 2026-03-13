# Project: Unnamed Talking Club

Jeopardy-style challenge board web app for Improv / Toastmasters club gatherings.

## Architecture

Single-page app with no build step, no dependencies, no backend.

| File | Purpose |
|------|---------|
| `index.html` | Complete app — all HTML, CSS, and JavaScript inline |
| `questions.txt` | Plain-text data file loaded at runtime via `fetch()` |
| `QUESTIONS.md` | Formatted table of all challenges (for sharing in chat) |

## questions.txt format

```
[Category Name]
1: Question text for level 1
2: Question text for level 2
3: Question text for level 3
4: Question text for level 4
5: Question text for level 5
```

- Categories: `[Name]` on its own line
- Questions: `N: text` where N is 1-5
- Blank lines are ignored
- Grid adapts to number of categories automatically

## Design system

Microsoft Fluent Design palette:

| Token | Value | Usage |
|-------|-------|-------|
| Primary blue | `#0078d4` | Headers, borders, Start button |
| Accent cyan | `#50e6ff` | Hover glow, level numbers, timer display |
| Background | `#1b1b1b` | Page background |
| Card bg | `#0e3a5e` | Question cells and overlay |
| Warning | `#ffb347` | Timer at ≤30s |
| Danger | `#d13438` | Timer expired, Stop button |
| Font | Segoe UI | Body text |
| Mono font | Cascadia Code / Consolas | Timer display |

## Key components in index.html

- **Board builder** — dynamically creates CSS grid from parsed categories
- **Overlay** — scale-up/fade animation via CSS transitions (`.backdrop.open`)
- **Timer** — countdown with Start/Stop/+/- controls, 1-10 min range, warning + expired states
- **Answered state** — tracked in a JS `Set`, dimmed via `.answered` class, resets on reload

## Conventions

- Everything stays in a single `index.html` — do not extract CSS/JS to separate files
- No external dependencies (no CDN, no npm packages)
- Serve with `npx serve .` for local development
- All event listeners attached via JS (`addEventListener`), not inline HTML attributes
- CSS animations use transitions, not JS animation libraries
