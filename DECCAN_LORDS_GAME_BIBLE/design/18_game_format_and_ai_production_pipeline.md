# 18 — Recommended game format, player flow and AI-assisted production pipeline

**Status: RECOMMENDATION FOR DISCUSSION — not fully locked**  
**Date:** 2026-10-17  
**Purpose:** Turn the user's game references, current historical observations and solo/AI-assisted development constraints into one practical direction. This recommendation should guide the first prototype without pretending that all content, formulas or historical institutions have been finalised.

## Executive recommendation

Build **a fixed-world kingdom strategy sandbox with real-time tactical battles, settlement development and emergent political/economic simulation**.

The strategic world starts from a researched, hand-authored historical/alternate-history state. It is not an empty random map that every player fills from zero. The world then evolves through shared simulation rules: rulers make decisions, parties travel, trade and war change holdings, households grow or leave, relationships change, and new kingdoms may rise.

- **Age of Empires:** take responsive RTS control, selection, commands, formations, battlefield clarity, readable counters and satisfying combat feedback.
- **Manor Lords:** take inhabited settlements, household and labour management, development, land suitability, local security and the connection between prosperity and population.
- **Anno 1800:** take production chains, warehouses, markets, goods flows, trade routes, household demand and economic trade-offs, simplified to fit the chosen historical period.
- **Mount & Blade: Bannerlord:** take a persistent strategic map, moving parties, independent lords, companions, relationships, changing allegiance, political opportunity and freedom to rise from local lord to ruler.

The result should feel like one game rather than four separate games joined together. The shared simulation should drive all layers, while each layer exposes only the controls and details useful to the player.

## 1. Recommended world format

### A fixed, researched world with a seeded political starting state

Use authored geography and meaningful settlement/route locations. At a chosen campaign start date, define which powers, lords, towns, forts, villages, ports, resources, roads and relationships exist. The campaign may then diverge from history through player and CPU decisions.

Do not combine every polity from 1500–1800 in the same starting state as if they all existed at once. A campaign start date determines the initial roster, while the simulation can produce an alternate future after that date.

The long-term geographic ambition from Delhi toward Kanyakumari remains a world-design ambition. Prove shared schemas, movement and simulation on a smaller representative region first; this is a vertical slice, not permission to discard the wider map.

### One world, with different views/detail levels

The recommendation is **not** a huge seamless 3D continent that simulates every villager and battle at full detail at once. Use distinct but connected views/scenes over the same persistent campaign state:

1. **Strategic campaign map:** see territory, settlement/fort icons or representations, roads, routes, parties, armies, caravans, known threats and political borders. Issue strategic movement, settlement, diplomacy, trade, patrol, raid and campaign orders.
2. **Local settlement view:** enter a player-owned or important contested settlement to inspect buildings, households, production, stores, security and construction. It remains linked to the same settlement state; leaving and returning should not reset inventories or people.
3. **Tactical battlefield or siege view:** when an encounter is chosen for manual battle, load a focused battlefield using the relevant region's terrain and context. Player and CPU control actual units in real time. Casualties, captured goods, morale, prisoners when included, commander outcomes, settlement damage and political consequences return to the campaign state after the battle.
4. **Interface panels and alerts:** many political, trade, household and administrative decisions should be available without forcing constant scene changes.

These can be separate Godot scenes that pass references/IDs to the same simulation state. Scene transitions are preferable to a first attempt at a seamless continent/local town/battlefield world. True seamless streaming can be researched later if it demonstrably improves the game.

### Campaign flow

A typical loop:

1. Inspect what the player's people need, what the treasury can afford, and what neighbouring lords or rulers are doing.
2. Improve a settlement, adjust labour/tax/security, establish production, buy or sell goods, or arrange trade/credit.
3. Receive a request, opportunity or threat grounded in the world state.
4. Decide whether to negotiate, honour an obligation, recruit, train, patrol, escort, spy, raid, move an army or prepare a defence.
5. Travel and interact with terrain, supply routes, forts, caravans and other parties.
6. Fight a tactical battle or siege when appropriate—or avoid it, negotiate, retreat or use logistics/intelligence to change the situation.
7. Apply casualties, recovery time, captured/lost inventories, treasury changes, damaged buildings, reputation, loyalty and political responses.
8. Let the world respond; recover and make the next decision.

The core pleasure is seeing a decision create consequences in several systems, not clicking through disconnected menus.

## 2. The player's identity and long-term progression

The player begins as a lord/clan leader in a specific historical situation, with holdings appropriate to that scenario. A town, fortress and several villages are not mandatory holdings for every noble. Rank, grants, territory, wealth, recognition, troops, relationships and historical circumstances shape the start.

The player should be free to pursue political growth: remain a lord, gain a larger appointment, support another claimant, change allegiance, become a mercenary/outlaw where supported, form a new kingdom or pursue imperial authority. These are campaign ambitions, not all guaranteed first-release features. The simulation should not invent rank advancement through one universal checklist until the historical system is researched.

## 3. Recommended art and camera direction

**Recommendation to test:** stylised, readable 3D with a three-quarter/isometric-like camera, grounded in Deccan/Indian architecture and landscape. Use modular, low-to-moderate-detail models, a coherent material/colour palette, warm atmospheric light, good silhouettes, readable team/faction colours, strong animations and layered sound. The aim is a polished, inviting strategy-game presentation—not high-poly photorealism.

Why not choose 2D pixel art immediately? It can be beautiful and may simplify some rendering, but this game needs armies moving in formations, terrain and fortifications viewed from several useful distances, distinctive Indian buildings, readable combat animation and potentially camera rotation/zoom. Pixel art still requires a large amount of unique directional sprite work. Reusable 3D models and rigs may be a better long-term fit for the chosen combination of systems.

This is a **recommendation, not a final art lock**. Build one small visual benchmark in Godot before deciding. It should include plateau/rock terrain, vegetation, one village, a small fort or wall, a market/building, a few animated people and soldiers, selection/movement, day/weather lighting treatment, UI and combat feedback. Compare quality, performance, iteration effort and the user's preferred look. Do not create hundreds of assets before approving the benchmark.

A solo developer with AI can make strong, polished work, but AI does not eliminate art direction, asset cleanup, rigging, animation consistency, testing or iteration. "AAA feel" should mean polish, cohesion and satisfying feedback—not an unsupported promise of AAA content volume or quality at zero cost.

## 4. Simulation complexity: realistic underneath, legible on top

The user has approved the hybrid household/workforce baseline. Continue with:
- Households and housing needs, population growth/migration, labour categories and job allocation.
- Local production choices shaped by terrain, water, climate/season, deposits, roads, security and market access.
- Actual inventories for important goods, warehouses, markets, prices at an appropriate level of abstraction and transport by caravans.
- Persistent merchants with capital, stock, routes, trust, debts, allies, rivals and contracts.
- Noble arrangements that vary by polity/rank/circumstances; political authority, revenue rights, remittance, salary, privileges and service duties remain distinct data.
- Lords, companions and parties with goals, traits, skills, relationships, knowledge, memory and constraints.
- Armies, temporary levies, professional troops, wages, supplies, rest/recovery, training, casualties and tactical battles.
- Forts, roads, patrols, intelligence and sieges whose location and logistics matter.
- Consequences that propagate between economy, people, war and politics.

Do not simulate every person as an elaborate autonomous agent. Use household/workforce groups for ordinary population; individual characters get greater detail when they have meaningful personal agency. Do not run every distant lord, household or navigation request every rendered frame. Use event-driven changes, controlled simulation ticks and cheaper aggregate updates at distance, while preserving causal consistency.

The player-facing interface should present consequences simply: clear alerts, priorities, short explanations, inspectable numbers and optional detail. Notifications inspired by Anno should be useful and prioritised, not an endless interruption stream.

## 5. Feature boundaries and delivery order

The idea list is the long-term vision, not a requirement to implement every feature before the game can be played. Features involving loans, court/succession rules, espionage, assassination, captivity, slavery/forced labour, religious policy, marriage/dynasty, custom fort building, complex siege machinery, or competitive multiplayer need separate design, research, ethical/tone decisions and acceptance tests.

### First vertical slice — recommendation

Build the smallest experience that proves the game identity:
- A small, representative strategic area with a few connected villages, one meaningful town/fort, roads and geography.
- One player lord, one neighbouring/overlord lord and a small set of relationships.
- One settlement with household/workforce assignment, a few meaningful needs and 2–3 geography-appropriate production activities.
- Inventory/warehouse and a simple market/trade interaction.
- One moving party/army and one caravan or patrol, with movement and a simple threat/escort/raid case.
- One tactical battle that can be controlled in real time and whose outcome updates the campaign.
- One meaningful political choice with a visible economic or military consequence.
- Save/load, a short onboarding flow, clear notifications, useful debugging and automated tests.
- A representative polished art/audio scene, not placeholder-only grey boxes as the final proof of direction.

Leave advanced contracts, full continent content, every historical faction, deep dynasty, all siege systems, multiplayer, and the complete historical roster out of this first proof unless one is essential to test the core.

### Suggested delivery sequence

1. **Environment and repository:** stable tools, project skeleton, version control, automated smoke check.
2. **Visual/technical benchmark:** terrain, camera, buildings, a handful of animated units, movement/selection/combat, import pipeline, performance capture.
3. **Simulation foundation:** data-driven definitions, explicit state-changing commands, separate simulation from rendering, deterministic small scenarios and debug logging.
4. **Core vertical slice:** connect one settlement/economy, one lord relationship, one moving party and one real-time battle.
5. **Playtest and tune:** test exploits, edge cases, performance, save/reload and user comprehension before expanding.
6. **Content expansion:** historical locations/factions, settlement variety, merchants, politics, sieges, deeper AI and polish in deliberately chosen increments.

Do not commit to a delivery date until this slice has run and been measured.

## 6. Recommended development stack, checked on 17 October 2026

- **Main engine:** Godot 4.7.2 stable was the latest stable release found on the official archive on the check date; 4.8 was still beta. Pin a stable patch for the project and revisit only through tested upgrades. Official archive: https://godotengine.org/download/archive/ and release policy: https://docs.godotengine.org/en/stable/about/release_policy.html
- **Gameplay language:** GDScript first, because the project is primarily a Godot gameplay/simulation project. Avoid adding C# or extra frameworks until a measured need justifies it.
- **3D creation:** Blender 5.2.2 LTS was available from the official Blender site on the check date: https://www.blender.org/download/lts/. Keep reusable source assets organised. Godot recommends glTF 2.0 (.glb/.gltf) as a strong interchange format; direct Blender-source import calls Blender during import and adds a dependency to the project workflow. Reference: https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/importing_3d_scenes/available_formats.html
- **Editor/AI coding:** VS Code plus the Codex IDE extension, signed in to the user's ChatGPT account, or Codex CLI running in the project directory. Codex usage limits depend on the plan and model; a Plus account should not be treated as unlimited. Official guide: https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan
- **Version control:** Git and GitHub. Markdown Game Bible remains the canonical design source. Use small branches/commits, clear change summaries and rollback ability.
- **Optional local models:** Ollama or another local runtime can be evaluated for documentation drafts, repetitive transformations, sample data, simple scaffolding and first-pass tests. Ollama documents a Codex CLI integration via ollama launch codex / codex --oss: https://github.com/ollama/ollama/blob/main/docs/integrations/codex.mdx. On a 16 GB Mac, choose a modest quantised model and measure speed/quality; do not assume local inference is always fast or capable enough. Use the stronger subscribed model for architecture, difficult bugs and critical review when its usage budget allows.
- **Optional Godot MCP:** Evaluate an open-source Godot MCP server only after the Godot project can launch and run headless. Candidate: https://github.com/blentz/godot-mcp, whose README describes tiered tools for project files, scene/resource operations, running and debugging; alternative candidate: https://github.com/Coding-Solo/godot-mcp, MIT-licensed and able to launch/run projects and retrieve debug output. Confirm current maintenance, licence, tool permissions, compatibility and path restrictions before choosing. Start with a limited tool set and keep destructive file/command operations under approval. MCP is a tool bridge, not an autonomous quality guarantee.
- **Documentation retrieval:** OpenAI's public docs MCP at https://developers.openai.com/mcp is read-only developer-documentation search. It may be useful inside Codex but it is optional, not needed to launch the game.

Current references were checked on 2026-10-17. Re-check releases when actually setting up the machine; never use a beta merely because it is newest.

## 7. Important boundary: what "controlled from ChatGPT" means

An ordinary browser ChatGPT conversation does not automatically gain access to local Mac files, Godot, Blender or terminal processes. To execute project work locally, the user must open the local repository in a tool that has those permissions, such as Codex IDE/CLI, and approve its access. A configured local MCP server can provide additional engine tools to that agent; the tools still operate within their permissions and need testing.

Use ChatGPT conversations for design, history analysis, plans and reviews; use Codex on the Mac for repository edits, scripts, engine launches and tests. Keep the shared GitHub repository as the hand-off point for canonical documentation and code. Do not assume that a change made in this browser conversation has automatically appeared in a local working tree until Git has fetched/pulled it.

## 8. Automated production loop and quality gates

Each feature should go through the same small loop:

1. Write a short feature contract: player problem, scope, data/state transitions, edge cases, acceptance criteria and what is explicitly out of scope.
2. Have Codex inspect the relevant Game Bible and existing code before editing.
3. Implement one coherent feature, keeping simulation logic separate from scene visuals and UI.
4. Run Godot headless project/import checks, automated unit/simulation tests and the relevant export/build check.
5. Run the game in the editor, inspect logs and screenshots/video, and manually evaluate the visual/gameplay result.
6. Test failure/edge cases and performance against a defined scene/entity count; check save/load and unintended side effects.
7. Review the diff and dependency/license impact. Fix failures before adding more features.
8. Update the Game Bible and decision log only when the implementation or design has changed; commit a small, reversible change.

Automate the checks that machines can reliably verify. Keep human approval for visual quality, game feel, historical interpretation, destructive operations and major scope decisions. A green build alone is not evidence that a strategy game is fun or polished.

## 9. Performance and art pipeline

Use data-driven building/unit/resource definitions and reusable asset kits. Prefer instancing for repeated scenery, level of detail/visibility ranges for distant models, and lower detail/update rates for distant simulation entities where profiling justifies them. Godot's official performance docs discuss culling, LOD, instancing and large-world considerations: https://docs.godotengine.org/en/stable/tutorials/performance/optimizing_3d_performance.html

Profile representative stress scenes containing a plausible count of moving troops, trees/buildings, path queries, effects and active NPCs. Do not set an arbitrary army-size or map-size limit before measuring, but do not promise unlimited armies or full-detail simulation everywhere before tests.

Use one coherent asset pipeline: consistent scale/origin/pivot, naming, material palette, collision/LOD policy, animation conventions, file formats and licences. Record third-party assets and their licence in a manifest. Never rely on scraped or unlicensed game art as final assets.

## 10. Main risks and guardrails

- **Scope sprawl:** keep long-term ideas in the Bible but limit the first slice to an integrated subset.
- **Mode mismatch:** do not promise both a deep persistent sandbox and a fully balanced competitive RTS on day one.
- **Simulation exploits:** test whether players can break the economy through loans, taxation, trade loops, loot or army wages; let clever strategies be possible without unbounded money exploits destroying every other system.
- **CPU omniscience:** NPCs should act on information they plausibly know; log major decisions and allow mistakes.
- **Performance:** measure navigation, animation, rendering, world updates and memory separately.
- **Historical compression:** keep one time-specific initial faction state; don't blend 300 years into an ahistorical opening.
- **Art consistency:** a small polished asset kit is preferable to many inconsistent AI-generated models.
- **AI overconfidence:** every generated change must be tested, reviewed and reversible. Do not grant a model unrestricted access to credentials or destructive commands.
- **Scope/quality trade-off:** the goal is a polished game. Feature counts and an elaborate architecture are not substitutes for a fun vertical slice.

## 11. Decisions still needed

The recommendation above intentionally leaves these open:
- Exact campaign start year and the initial historical/alternate-history boundary.
- Exact strategic map boundaries and the first prototype region.
- Whether the suggested strategic/local/tactical scene transitions feel right to the user, versus a single continuous map.
- Visual benchmark approval: stylised low-detail 3D versus another art treatment.
- Campaign time control (pause/slow/normal/fast) and exact tactical pause/order behaviour.
- Exact first-slice resources, buildings, merchant contract and political interaction.
- Battle size, unit count, formations, manual control details, siege scope and defeat/recovery rules.
- First-release scope; all long-term ambitions are not automatically v1 features.
- Local-model choice and whether a Godot MCP measurably improves development after the project boots reliably.

The immediate priority is to agree on the overall flow and prove it with a small polished playable slice. The rest of the detailed design should be informed by the user's master history and the results of actual prototypes.
