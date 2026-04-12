---
role: qa
owner: Gerald
status: active
last-updated: 2026-04-12
---

# QA

## Scope
Owns "does it actually work?" For a static site that means: pages load, links resolve, games are playable on desktop and mobile browsers.

## Decisions
| Date | Decision | Rationale | Linked roles |
|---|---|---|---|
| 2026-04-12 | Manual smoke test only for v1: open index.html, click each card, verify game loads and responds to input. No automated test suite. | Two pages, no logic in the landing page. Automation would exceed the surface area. | [[dev]] |

## Dead Ends
<!-- APPEND ONLY. Never delete. -->
| Date | What was tried | Why it failed / was rejected |
|---|---|---|

## Lessons

## Open Questions
- [ ] Do the games work on touch devices, or is input assumed keyboard/mouse? Not yet tested after the rename. — owner: Gerald — since: 2026-04-12
- [ ] If readability is eventually measured by a real QR decoder, how do we regression-test "a scannable QR still decodes at pixel-coverage X"? — owner: Gerald — since: 2026-04-12

## Assumptions
- [the existing games still function identically after being moved into games/] — status: untested — since: 2026-04-12

## Dependencies
Blocked by: [[dev]]
Feeds into: [[pm]]

## Session Log
- 2026-04-12 — Scope set. Manual smoke test only for v1.
