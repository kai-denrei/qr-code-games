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
- 2026-04-12 — Scaffolded folder structure. Moved existing games into `games/`. Created landing page.
