---
project: qr-code-games
created: 2026-04-12
status: active
mode: solo
stale_threshold_days: 30
---

# qr-code-games — Index

## Brief
A series of 8-bit-reminiscent mini-games where something progressively destroys or eats the pixels of a QR code. The playful question each game asks is: *at what point does the QR code stop being readable?* Each iteration explores a different destruction mechanic (invader-style shooting, snake-style consumption, more to come). A simple landing page lets the player pick which game to play.

## Active Roles
- [[dev]] — owner: Gerald
- [[arch]] — owner: Gerald
- [[pm]] — owner: Gerald
- [[ux]] — owner: Gerald
- [[qa]] — owner: Gerald
- [[devops]] — owner: Gerald

## Key Decisions
<!-- Cross-role summary, maintained by COMPACT -->
- 2026-04-12 — Static HTML/JS, no build step. Each game is a standalone file. See [[dev]], [[arch]].
- 2026-04-12 — Landing page is a game picker, not a hub. No score sharing, no metagame. See [[ux]], [[pm]].
- 2026-04-12 — The two games intentionally diverge in interaction model: QR Invader is a clockwork demo (no player input), QR Snake is a click-to-carve time trial. See [[pm]], [[dev]], [[ux]].
- 2026-04-12 — Invader emotion state borrows vocabulary and braille faces from the sibling Braille Lab emotion module (kai-denrei/braille-lab). Four states: determined / frustrated / angry / glee. See [[ux]], [[dev]].

## Open Questions (cross-role)
- [ ] Does the QR encode something meaningful (URL, message, joke) so the "still readable?" moment has a payoff? — owner: Gerald — since: 2026-04-12 — touches [[pm]], [[ux]], [[dev]]
- [ ] How is readability actually verified during gameplay — real scanner, in-browser decoder, or just a computed coverage metric? — owner: Gerald — since: 2026-04-12 — touches [[dev]], [[qa]]
- [ ] Should the snake game also grow a terminal/emotion panel to match the invader's, or is its muted aesthetic intentional for contrast? — owner: Gerald — since: 2026-04-12 — touches [[ux]], [[pm]]
