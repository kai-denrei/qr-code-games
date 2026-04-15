---
role: ux
owner: Gerald
status: active
last-updated: 2026-04-12
---

# UX / Design

## Scope
Owns how it feels. 8-bit, pixel-honest, playful. The landing page must not undermine the aesthetic of the games themselves.

## Decisions
| Date | Decision | Rationale | Linked roles |
|---|---|---|---|
| 2026-04-12 | Landing page: dark background, monospace font, two large pixel-bordered cards. Each card previews the game name and destruction mechanic in one line. | Matches the arcade/terminal vibe of the games (especially qr-snake's Share Tech Mono + #0d0d12 palette). A slick modern landing page would clash. Rejected: light/minimal cards (they read as "SaaS", not "arcade"). | [[pm]], [[dev]] |
| 2026-04-12 | No hero copy, no "about" section, no footer nav. Just title, two cards, one-line tagline. | The games are the pitch. Copy would delay the click. | [[pm]] |
| 2026-04-12 | Invader intro is a 3-phase 4 s animation: (1) enters from off-frame top, straight-at-viewer zoom 1×→16×; (2) hovers huge dead-center for 1 s with pulsing halo + bob; (3) spiral descent (2.5 turns, 110 px max radius) shrinking 16×→1× into the spawn cell. | User wanted "bigger, more in your face, 2× hover, then dive". Phase timings (`P1=0.30`, `P2=0.55`) are the main dials. | [[dev]] |
| 2026-04-12 | Invader emotion state is displayed in a mock-terminal block above the QR. Format: `emotions@qr-invader:~$ show <name>_` with a 4×2 braille face below. Color + braille face swap together on state changes. | Replicates the Braille Lab emotions module visual; gives the sprite's color shifts a semantic handle in plain language. Rejected: dynamic "Nominal/Degraded/Critical" status text (was pulling focus from the braille). | [[dev]] |
| 2026-04-12 | Color→emotion mapping: purple=determined, orange=frustrated, red=angry, dark red=angry (deepens without changing the label), teal=glee. Both red tiers share the `angry` label so the terminal doesn't flicker mid-rage. | User-specified palette. Keeping the label stable across the two red stages avoids visual noise; color still conveys intensity. | [[dev]] |
| 2026-04-12 | "READ THE CODE BEFORE IT IS TOO LATE!" is a fixed Press Start 2P warning above the terminal. Readability% drives its *color* (green → amber → red) but never the text. | Fixed hero message reads as an 8-bit warning poster. Dynamic text would reduce it to a status line. | [[dev]] |
| 2026-04-12 | Snake win overlay is semi-transparent (`rgba(13,13,18,0.62)` + 4 px backdrop blur), pinned top-center via `position:fixed`, max-width leaves room for the back button. | User explicitly wanted the QR scannable while the win panel is visible, so the panel must float above — not replace — the canvas. Rejected earlier full-screen blackout. | [[pm]] |

## Dead Ends
<!-- APPEND ONLY. Never delete. -->
| Date | What was tried | Why it failed / was rejected |
|---|---|---|
| 2026-04-12 | Snake eat-on-impact mechanic (hold space / tap on wall collision to bite QR pixels). | User reported the snake got "stuck in a navigating/turning back loop when too long" and explicitly asked to remove the eat action. Replaced with click-to-carve + apple goal. |
| 2026-04-12 | Anger accumulator driven by wall hits (`ANGER_INC=0.22` per hit, `ANGER_DEC=0.08` per free move, post-fire cooldown). | "Too angry too often" — the QR maze has enough walls that hits dominate moves, so bursts felt near-constant. Replaced with a pure timer-driven state machine (calm 7–13 s → phased rage → glee → calm). |
| 2026-04-12 | Square bounding-box halo behind the angry invader (beige/pink fill rect). | User called it out as looking like a "square filling". Replaced with `ctx.shadowBlur` glow that hugs the sprite's outline. |
| 2026-04-12 | Initial `lastEmotionName='determined'` sentinel in the terminal initializer. | `setTerminalEmotion('determined')` short-circuited on the first call due to the dedup guard, so the braille face stayed blank until the first rage started. Fixed by initializing `lastEmotionName=''` and calling `setTerminalEmotion('determined')` explicitly at boot. |

## Lessons

## Open Questions
- [ ] Should the landing cards show a live/animated mini-preview of each destruction mechanic, or is a static screenshot / icon enough? — owner: Gerald — since: 2026-04-12
- [ ] qr-invader uses a light palette, qr-snake uses a dark one. Do we harmonize them or let each game own its vibe? — owner: Gerald — since: 2026-04-12

## Assumptions
- [dark theme for the landing page will not feel jarring against qr-invader's light theme on click-through] — status: untested — since: 2026-04-12

## Dependencies
Blocked by:
Feeds into: [[dev]]

## Session Log
- 2026-04-12 — Invader dramatic intro, emotion terminal with braille faces, Press Start 2P warning banner, snake win overlay made semi-transparent so the QR stays scannable underneath. Four rejected approaches recorded as dead ends.
- 2026-04-12 — Landing page designed: dark, monospace, two cards, no chrome.
