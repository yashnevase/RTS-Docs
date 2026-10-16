# 10 — Scope and delivery approach

## Primary recommendation

Use Godot for the main build after a small engine validation slice. Do not implement the entire game in React/HTML and then rebuild it in Godot; that duplicates systems, creates divergent behavior and consumes time. Keep the current Three.js project as a reference and selectively reuse/port mechanics after inspection.

## Milestone sequence — provisional

### Stage A — Vision and proof of direction
- Keep this living bible as the source of truth.
- Finalize the intended view/camera and broad time/scale model.
- Build a Godot scene with a small landscape, one settlement, a few buildings, animated units, camera/selection/movement, lighting, ambient sound and a simple combat interaction.
- Verify the scene imports/exports, runs acceptably on target hardware and provides the desired feel.

### Stage B — Core vertical slice
- Playable opening scenario with inherited holdings.
- One local settlement with a first-pass household/workforce and production model.
- One field army and one fortification.
- One AI lord with a goal and one meaningful political interaction.
- One battle that changes the campaign state.
- Save/load, tutorial/help and basic debug logs.

### Stage C — Integrated campaign prototype
- Strategic map routes and settlement control.
- A small number of active lords/factions with different goals.
- Economy, recruitment, supplies, relationships, events and outcomes integrated.
- Test a complete loop: improve settlement → make decision → face reaction → recover/reward/consequence.

### Stage D — Content and presentation expansion
- Add regions, settlements, units, structures, events, sound, animation, balance and UI only after the core loop is enjoyable and testable.

### Stage E — Release hardening
- Performance profiling, save/load recovery, onboarding, accessibility, installer/export pipeline, playtests, bug fixing, licensing and storefront preparation.

Timings are intentionally not promised yet. Scope and the available work schedule are not established well enough for honest estimates.

## Scope and scale controls

- Preserve the large fixed-map ambition. A vertical slice is a small test of the systems, not a decision to shrink the intended world.
- Reuse the same entity schemas and simulation rules across the map. Prove that new places and lords can be defined mostly through data rather than bespoke code.
- Evaluate cheaper update cadences or aggregate calculations for distant entities only as performance techniques; they must still react consistently to world conditions and remain part of the same living world.
- Add a resource/building/stat only when it creates a decision worth the complexity.
- Test any new system with a concrete player scenario and edge cases.
- Do not call the game ready because it compiles; require a playable, repeatable loop and defined quality bar.

## Definition of vertical-slice success

A player can start, understand the clan's immediate situation, manage a settlement, issue an army command, interact with a lord, experience a simulated consequence, fight or avoid a battle, and save/reload without state corruption. The slice should also demonstrate the intended art and audio quality at target performance.
