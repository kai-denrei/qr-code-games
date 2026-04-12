---
role: dev
owner: Gerald
status: active
last-updated: 2026-04-12
---

# Development

## Scope
Owns the code. Each game is a self-contained HTML file. The landing page is also a single HTML file. No framework, no build step, no package.json — until one is justified.

## Decisions
| Date | Decision | Rationale | Linked roles |
|---|---|---|---|
| 2026-04-12 | One standalone HTML file per game. No bundler, no shared JS yet. | Games already exist as standalone files. Sharing code before the second duplicate pattern emerges is premature. Rejected: extracting a shared `qr-core.js` module. | [[arch]] |
| 2026-04-12 | Landing page at `index.html`, games in `games/`. Renamed `qr_invader_v2.html` → `games/qr-invader.html`, `qr_snake_v2.html` → `games/qr-snake.html`. | Flat structure. `_v2` suffix was version noise — version lives in git, not in filename. | [[ux]] |
| 2026-04-12 | No client-side router. Landing page uses plain `<a href>` links. | Two pages. A router would be cosplay. | [[arch]] |
| 2026-04-12 | QR Invader is a pure autonomous demo — all click/tap/key handlers removed. Invader wanders via random walk inside a 2×-scale QR maze (`MOD=20`). | The "watch QR pixels get destroyed" premise doesn't need a verb from the player. Removed the shooter mechanic entirely. | [[pm]], [[ux]] |
| 2026-04-12 | Rage is a **timer-driven state machine** with phase-based dwells, not a linear anger ramp. Phases: FRUSTRATED 1500 ms / RED 450 ms / DARK_RED 450 ms → fire → GLEE 2000 ms → calm 7–13 s. | A linear ramp couldn't hold visibly on the orange "frustrated" stage. Rejected the earlier wall-hit accumulator (too frequent, too integer-step). Phase constants are easy to tune. | [[ux]] |
| 2026-04-12 | Snake is fixed length 3, never grows. Player click/tap destroys QR pixels via `carveAt`; snake wanders autonomously and wins when its head reaches a randomly-placed apple. `isBody` collision disabled during 180° trample fallback so the snake can walk through itself to escape dead ends. | The old eat-on-impact mechanic caused stuck-on-wall loops the user explicitly rejected. Click-to-carve cleanly separates player agency (path shaping) from snake agency (navigation). | [[pm]], [[ux]] |
| 2026-04-12 | Invader emotion names and braille faces are sourced from the sibling `kai-denrei/braille-lab` emotion module. Local `BRAILLE_FACES` map is the authoritative snapshot for this game — not imported at runtime. | Avoids a cross-repo build coupling for a 4-entry lookup table. Faces can drift; revisit if Braille Lab adds a shared runtime. | [[ux]] |

## Dead Ends
<!-- APPEND ONLY. Never delete. -->
| Date | What was tried | Why it failed / was rejected |
|---|---|---|

## Lessons

## Open Questions
- [ ] How should readability be measured in-game? Options: (a) pixel coverage %, (b) run a real QR decoder on the canvas each frame, (c) both. — owner: Gerald — since: 2026-04-12
- [ ] Do the existing v2 games already share any code worth extracting, or are they diverging enough to stay independent? — owner: Gerald — since: 2026-04-12

## Assumptions
- [static hosting is fine; no backend needed for v1] — status: untested — since: 2026-04-12
- [both existing games work without modification after the rename/move] — status: untested — since: 2026-04-12

## Dependencies
Blocked by:
Feeds into: [[qa]], [[devops]]

## Session Log
- 2026-04-12 — Invader rewritten as autonomous demo. Added timer-driven phase-based rage state machine, emotion-mapped mock terminal with braille faces, 3-phase 4 s dramatic intro. Snake reworked into a click-to-carve apple-reaching game with 180° trample fallback for dead-end navigation.
- 2026-04-12 — Scaffolded folder structure. Moved existing games into `games/`. Created landing page.
