# qr-code-games

A small series of 8-bit-style mini-experiments about destroying QR codes.

> The question each iteration asks: **at what point does a QR code stop being readable?**

## Games

- **[QR Invader](games/qr-invader.html)** — autonomous demo. A tiny pixel-art invader descends into the QR maze, wanders around, and periodically rages through a visible emotion ramp (determined → frustrated → angry → glee) before firing a projectile that chews a hole in the code.
- **[QR Snake](games/qr-snake.html)** — an apple-reaching game. A short snake wanders the QR maze on its own; the player clicks to carve out QR pixels and open paths, racing to guide the snake to a random apple while keeping the code scannable. Reaching the apple triggers an `APPLE REACHED — FORBIDDEN KNOWLEDGE UNLOCKED` overlay, positioned so the QR stays scannable underneath.

The landing page at [`index.html`](index.html) is a dark, monospaced picker that links to both games.

## Emotion module

The invader's emotional state is mapped to a braille face rendered in a mock terminal above the QR, drawing the expression vocabulary from the sibling [Braille Lab](https://kai-denrei.github.io/braille-lab/emotions/) project.

| Color       | Emotion      |
|-------------|--------------|
| Purple      | Determined   |
| Orange      | Frustrated   |
| Red / Dark red | Angry     |
| Teal        | Glee         |

## Running locally

It's static HTML/JS with no build step. Any static server works:

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Decision log

`.deban/` is the project memory vault (role-scoped decision logs for dev, arch, pm, ux, qa, devops). See `.deban/_index.md` for the brief and the cross-role decision summary.
