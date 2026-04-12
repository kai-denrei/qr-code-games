---
role: pm
owner: Gerald
status: active
last-updated: 2026-04-12
---

# Product

## Scope
Owns *why this exists* and *what "done" looks like* for each iteration. Keeps the core question sharp: "when does the QR stop being readable, and is that moment fun?"

## Decisions
| Date | Decision | Rationale | Linked roles |
|---|---|---|---|
| 2026-04-12 | First milestone is scaffold + landing page + two imported games. Gameplay tuning deferred. | Get the selection flow working before investing in mechanics. Cheap to throw away. | [[dev]], [[ux]] |
| 2026-04-12 | Scope is "several iterations" of the same core mechanic, not a single polished game. | The series *is* the product — each iteration is an experiment on a destruction pattern. | [[arch]] |
| 2026-04-12 | The two games intentionally diverge in interaction model. Invader = clockwork demo, Snake = active time trial. | After several rounds of tuning, each game settled into a different player-agency shape. Forcing them to share a model would lose what each already does well. | [[dev]], [[ux]] |

## Dead Ends
<!-- APPEND ONLY. Never delete. -->
| Date | What was tried | Why it failed / was rejected |
|---|---|---|

## Lessons

## Open Questions
- [ ] Does the QR need to encode something meaningful (URL to a joke page, secret message, redeem code) for the "is it still readable?" beat to land? — owner: Gerald — since: 2026-04-12
- [ ] Is "several iterations" 3? 5? 10? No definition of done for the series. — owner: Gerald — since: 2026-04-12
- [ ] Is this a toy, a portfolio piece, or a shareable web thing? Target audience undefined. — owner: Gerald — since: 2026-04-12

## Assumptions
- [the core loop of watching a QR get eaten is actually fun for more than ~30 seconds] — status: untested — since: 2026-04-12
- [players care about the "still scannable?" reveal moment enough to test-scan with their phone] — status: untested — since: 2026-04-12
- [two games is enough variety for a v1 landing page; more would be premature] — status: untested — since: 2026-04-12

## Dependencies
Blocked by:
Feeds into: [[dev]], [[ux]]

## Session Log
- 2026-04-12 — Two games diverged into distinct interaction models (demo vs time-trial). v1 considered feature-complete and pushed for review.
- 2026-04-12 — Brief recorded. 3 untested assumptions and 3 open questions surfaced during init challenge.
