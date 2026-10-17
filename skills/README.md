# DECCAN LORDS Codex skills

These project-specific skills are designed for a **Godot + Blender desktop strategy game**. They borrow the high-level workflow pattern of a director skill, narrow specialist skills, deterministic testing and evidence-based QA from [majidmanzarpour/threejs-game-skills](https://github.com/majidmanzarpour/threejs-game-skills), but they do not copy its Three.js scaffold or browser-only test scripts.

## Skills

- `deccan-lords-director`: route a task to the right specialist, preserve scope and integrate the result.
- `deccan-lords-gameplay-simulation`: Godot gameplay, economy, entities, campaigns, armies and explainable NPC logic.
- `deccan-lords-visual-assets`: stylised 3D art direction, Blender source assets, Godot import, asset reuse and licences.
- `deccan-lords-ui-ux`: RTS controls, menus, alerts, readability and accessibility.
- `deccan-lords-debug-profiler`: isolate runtime faults and profile the actual bottleneck.
- `deccan-lords-qa-release`: reproducible tests, headless checks, builds, screenshots and release evidence.

## Install into the actual game project

This repository is the design/documentation source. Once the Godot game project folder is chosen, run the install helper from this repository:

```bash
bash scripts/install_deccan_lords_skills.sh /absolute/path/to/the/game-project
```

The helper copies these skill folders to `.agents/skills/` inside that game project. It refuses to overwrite an existing skill directory. Inspect the files before installing; review any updates through Git.

The game project's root should also contain or have a reliable local link to `AGENTS.md`, `PROJECT_CONTEXT.md` and the Game Bible. The director skill checks for these sources and does not invent missing context.

Do **not** install the upstream `threejs-game-director` as the main DECCAN LORDS workflow: its packaged scaffold and QA scripts target Vite, Three.js and browser automation. Its orchestration/evidence methodology is useful, but Godot needs engine-specific scenes, import/export checks, simulation tests and performance capture.

All Godot gameplay remains GDScript-first unless a measured technical need justifies another language. A local model or MCP is optional; neither is a prerequisite for beginning the first playable slice.
