---
role: arch
owner: Gerald
status: active
last-updated: 2026-04-12
---

# Architecture

## Scope
Owns how the pieces fit. For a static site with two independent games, this role is deliberately thin until scale demands more.

## Decisions
| Date | Decision | Rationale | Linked roles |
|---|---|---|---|
| 2026-04-12 | Static site. No framework, no build, no dependencies. | Two HTML files and a picker. Any tooling would exceed the code it produces. Rejected: Vite + per-game module, rejected as ceremony. | [[dev]] |
| 2026-04-12 | Each game owns its own state and assets inline. Shared code is forbidden until a third game proves the pattern. | Rule of three. Two games can diverge freely; extraction after three reveals which abstractions are real. | [[dev]] |

## Dead Ends
<!-- APPEND ONLY. Never delete. -->
| Date | What was tried | Why it failed / was rejected |
|---|---|---|

## Lessons

## Open Questions
- [ ] At what point (3rd game? 5th?) does a shared `games/_lib/qr.js` for QR generation and pixel buffer management become worth extracting? — owner: Gerald — since: 2026-04-12

## Assumptions
- [the games will stay small enough that inline-everything remains readable] — status: untested — since: 2026-04-12

## Dependencies
Blocked by:
Feeds into: [[dev]], [[devops]]

## Session Log
- 2026-04-12 — Agreed: no build system. Rule-of-three policy for shared code extraction.
