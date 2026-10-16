# 08 — Technical architecture and AI-assisted workflow

## Provisional stack direction

**PROPOSED: Godot 4.x, using the latest supported stable patch at project setup, with GDScript for gameplay logic.** The intent is to use an integrated game engine for scenes, 3D rendering, animation, audio, UI, input and desktop export rather than build the entire product in React/Three.js and later rewrite it. Verify the current stable version and pin it in project setup; do not use an untested development/nightly build for the main project.

Godot officially supports native macOS development and Windows desktop exporting. Reference: [Godot Windows export documentation](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_windows.html) and [Godot platform FAQ](https://docs.godotengine.org/en/stable/about/faq.html).

## What to do with the existing Three.js prototype

- Keep it in version control as a reference/prototype.
- Audit movement, selection, combat, pathfinding, structures, resources, and screenshot style.
- Record desired behaviors and edge cases before adapting anything.
- Port or reimplement only components that are valuable and fit the chosen architecture.
- Do not build a second complete version of the campaign in React first.

A tiny React/HTML mockup is acceptable if it validates a UI interaction quickly; it must not become a parallel full-game implementation.

## Architecture principles

- Simulation state is separate from rendering and UI.
- State-changing actions are explicit commands validated by game rules.
- Data for buildings, units, goods, factions and events is data-driven where useful.
- Save/load has versioned schemas and deterministic migration tests.
- AI decision logic is modular, explainable and testable independently of rendering.
- Rendering/animation runs at frame cadence; settlement and political simulation run on controlled update cadences.
- No subsystem may silently invent state transitions owned by another subsystem.
- Use Git branches/commits and automated tests for meaningful work; avoid broad unreviewed AI edits.

## AI coding workflow

1. Human + assistant agree a small feature spec and acceptance criteria.
2. Codex implements only that scope.
3. Build/import/headless tests run; capture screenshots or logs for visual changes.
4. Review edge cases, performance, save compatibility and regressions.
5. Update the bible and decision log after decisions change.

## Local models and paid model use

A local model via a local runtime such as Ollama may help with repetitive drafts, sample data, tests, documentation and first-pass utility code. A stronger coding model should handle architecture, complex integration, critical debugging and final reviews. Local inference can reduce external usage, but code and data still need tests and licence/security review. Never grant an untrusted model unrestricted shell, filesystem or secret access by default.

## MCP policy

Add an editor MCP integration only after confirming it is maintained, compatible with the pinned Godot version, permission-scoped, and useful for real tasks. MCP is an interface to tools, not a substitute for specs, tests, version control or review.

## Performance and target platforms

Primary target: Windows PC distribution. macOS is the development environment and may also be a release target. Minimum CPU/GPU/RAM, frame-rate target, resolution, army count, entity budgets and save size are OPEN and must be tested against a representative scene.

## Future multiplayer preparation

Keep commands and state transitions explicit, but do not build online infrastructure before the single-player core is proven. Multiplayer would require separate choices for authority, session hosting, synchronization, persistence, rejoin behavior, anti-cheat and disconnect recovery.
