# 12 — Decision log

Use one entry per meaningful decision. When a decision changes, keep the old entry and add a new one with date, reason, and affected documents. Do not erase design history silently.

| ID | Date | Topic | Status | Current record | Next action |
|---|---|---|---|---|---|
| D-001 | 2026-10-15 | Product goal | PROPOSED | PC strategy sandbox combining approachable RTS loops, settlement development, political sandbox play, and reactive NPC lords | Refine player journey and audience priorities |
| D-002 | 2026-10-15 | Setting | OPEN | 17th-century India/deep Deccan focus; exact start year and launch map scale unresolved | Pick year and first playable region after user shares desired details |
| D-003 | 2026-10-15 | Starting story | PROPOSED | Young heir to a respected but politically constrained clan inherits modest villages/town/fortifications after father’s legacy; Sultan entrusts greater power to an experienced lord | Define event, holdings, allies, rivals and first dilemma |
| D-004 | 2026-10-15 | Main engine | PROPOSED | Godot 4.x stable for the main PC game; preserve Three.js prototype as reference and selectively reuse logic | Validate with one representative scene before full migration |
| D-005 | 2026-10-15 | React/HTML prototype | PROPOSED | Do not build the complete campaign in React first; use lightweight mockups only when useful | Proceed directly to a Godot vertical slice after requirements are clearer |
| D-006 | 2026-10-15 | Simulation model | PROPOSED | Separate rendering from simulation; use controlled update cadence and data-driven systems | Define state/time model later |
| D-007 | 2026-10-15 | NPC AI | PROPOSED | Start with utility scoring/planning/tactical state machines and explainable randomness; evaluate ML only for a measured benefit | Design a sample lord decision model after core gameplay loop is described |
| D-008 | 2026-10-15 | Population | PROPOSED | Inhabited settlements; housing/household growth, labor roles, demand fulfilment, taxes and safety affect prosperity/loyalty | Decide household versus person abstraction and growth rules |
| D-009 | 2026-10-15 | Logistics | PROPOSED | Separate supply convoy may travel slower than army and be raided/intercepted | Test whether this creates fun without excessive micromanagement |
| D-010 | 2026-10-15 | Multiplayer | DEFERRED | Long-term vision for session-based players taking lord roles, alliances, votes and wars; not first implementation target | Revisit after single-player campaign loop is proven |
| D-011 | 2026-10-15 | Geographic scale | OPEN | User's long-range vision extends Delhi to Kanyakumari; detailed launch footprint and per-location simulation are undecided | Compare full-map abstraction versus regional launch |
| D-012 | 2026-10-15 | Art style | OPEN | Existing prototype is a visual reference; target is polished stylized 3D with atmospheric audio and readable battles | Build Godot art/animation benchmark scene |
| D-013 | 2026-10-16 | Game identity | OPEN | Recent discussion leans toward a real-time settlement/kingdom sandbox with political simulation and tactical battles, rather than a pure short-match RTS | Decide the primary repeated activity and match/campaign relationship |
| D-014 | 2026-10-16 | AI-assisted development workflow | PROPOSED | Private Git repository + canonical Markdown + root `AGENTS.md` + Codex VS Code extension; optional ChatGPT GitHub read integration; optional Godot MCP after validation | Establish repository and baseline workflow before implementing the game |
| D-015 | 2026-10-16 | Audience and launch strategy | OPEN | Accessible surface, deep long-session play and polished PC release are goals; Steam/Epic reach and Stardew-like success are ambitions, not assumptions | Build vertical slice, playtest, then validate positioning and demand |
| D-016 | 2026-10-16 | World scale | OPEN | Long-term world aspiration spans major Indian powers from Delhi toward Kanyakumari; launch detail scale remains unknown | Compare full India simulation with a focused active region and expandable world model |

## Change log

### v0.1 — 2026-10-15
Captured the user's expanded vision and key open questions. No detailed formulas, exact content counts, release scope or historical faction roster have been locked by this file.


### v0.2 discussion sync — 2026-10-16

- Added the current genre/audience hypothesis without locking the final label or modes.
- Recorded that the AI-assisted development story shared by the user is a workflow idea to evaluate, not a proven recipe for AAA quality or guaranteed commercial success.
- No release scope, mode list, exact region, formulas or sales targets are locked by this update.
