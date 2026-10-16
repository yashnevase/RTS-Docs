# ChatGPT + VS Code + Codex workflow

This file explains how to make this discussion and the local repository work together. There is no automatic magical sync between an ordinary ChatGPT chat and an arbitrary local VS Code folder; use Git and canonical Markdown as the bridge.

## Recommended division of work

- **This ChatGPT conversation:** design partner, research, trade-offs, reviewing the game's identity, turning your explanation into explicit rules, and identifying open questions.
- **Game Bible Markdown:** durable project memory and source of truth. Store agreed decisions here; record proposals as proposals until confirmed.
- **Codex IDE extension in VS Code:** reads and edits your local repository, works on code/docs, runs approved commands and tests, and reviews diffs. Sign in with the same ChatGPT account; usage limits still apply.
- **GitHub:** backup/version history and bridge between local files and ChatGPT's GitHub connection when available.
- **Local LLM via Ollama:** optional helper for repetitive data generation, test-case drafts, documentation and low-risk utility work. Do not trust its code or install commands without review.

## Setup sequence on the Mac

1. Create a **private GitHub repository** for DECCAN LORDS. Use Git from the beginning; make small commits after accepted changes.
2. Copy `AGENTS.md`, `PROJECT_CONTEXT.md`, `CHATGPT_VSCODE_WORKFLOW.md`, and the `DECCAN_LORDS_GAME_BIBLE/` folder into the repository root. Commit them as the initial design baseline.
3. Install VS Code, the official Codex IDE extension, Git, and a stable Godot release. Sign Codex in using the intended ChatGPT Plus account. Open the repository root as the workspace.
4. In the ChatGPT interface, connect the GitHub app and authorize access only to this repository if the app is available for the account/surface. The ChatGPT GitHub integration is for repository reading/search in supported experiences; use Codex locally for edits. Do not assume GitHub-connected ChatGPT can push commits.
5. Keep `AGENTS.md` at repo root so Codex sees the project rules. At the start of a task, ask Codex to read `PROJECT_CONTEXT.md`, the Game Bible README, the relevant system page, open questions and decision log.
6. At the end of a design discussion, ask for a short **design sync summary** containing: confirmed decisions, proposals still open, changed assumptions, research to verify, and which Markdown sections should change. Update the Markdown through an explicitly reviewed edit/patch, then commit.
7. Commit and push accepted Markdown changes. ChatGPT can then read the committed state through GitHub in supported experiences. Uncommitted local edits won't necessarily be visible through that connection.
8. After the first Godot test scene exists, consider adding **one** maintained, compatible Godot MCP integration if live scene inspection, running, screenshots or editor manipulation would materially improve the workflow. Pin versions and keep Git diffs/backups. Start with minimum necessary tool permissions; more tools do not automatically mean better output.

## Design sync message template

Copy this into Codex after a design discussion:

> Read `AGENTS.md` and `PROJECT_CONTEXT.md`. Update only the relevant canonical Game Bible Markdown files with the design summary I provide. Do not invent missing rules. Keep all ideas marked PROPOSED or OPEN unless explicitly confirmed. Update `design/12_decision_log.md` and `CHANGELOG.md` when appropriate. Preserve history, repair relative links if needed, show a diff summary, and do not change gameplay code. Then list the remaining decisions.

## Implementation task template

> Read `AGENTS.md`, `PROJECT_CONTEXT.md`, and the relevant Game Bible pages. Implement only this vertical slice: [specific feature]. Acceptance criteria: [observable results]. Do not add unapproved systems. Work on a branch, keep changes small, run the relevant Godot parse/import/headless tests, capture a screenshot if visual behavior changed, inspect your diff, and report exact tests/results plus remaining risks. Do not claim tests passed unless they actually ran.

## Token/usage discipline

- Ask for one well-scoped feature per implementation task, not “build the whole game.”
- Keep current architecture and relevant system specs concise and linked; do not paste the entire bible into every prompt.
- Use local models for low-risk drafts and data. Use Codex for integrated edits and the strongest available model/effort for architecture, systemic bugs, and final reviews.
- Build repeatable scripts/tests once and reuse them. Automate import/parse checks, deterministic simulation tests and screenshot capture before increasing tool complexity.
- ChatGPT Plus/Codex allowances are limited and can vary by plan, model, context and task complexity. Local LLMs help reduce some usage but aren't a guarantee of equivalent code quality.

## Security and asset hygiene

- Never store API keys, passwords or personal secrets in the repository or prompts.
- Review commands that delete files, alter system settings, install packages or access network services.
- Check each asset's licence, attribution, commercial use and redistribution rights; keep a `CREDITS_AND_LICENSES.md` as assets are added.
- Commit before large AI changes and review the diff before accepting it.
