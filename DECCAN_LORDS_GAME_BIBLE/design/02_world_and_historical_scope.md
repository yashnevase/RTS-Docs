# 02 — World, geography and historical scope

## User's current ambition

The broad ambition is a map spanning a large part of the subcontinent—from the Delhi region toward Kanyakumari—with major historical cities, towns, villages, forts, ports and local power centers. Some settlements may grow into larger towns/cities; neglected or devastated places may temporarily become ruins and later recover. The Deccan is the narrative and political starting point, not necessarily the permanent geographic limit of the dream game.

## Major scale warning

A map covering most of India, with all settlements simulated at village-level detail, all lords active, evolving populations, supply convoys, wars and diplomacy, is a very large content and simulation problem. The key design decision is not simply “small map or large map”; it is **which level of detail is simulated at each scale**.

Possible layered model to evaluate:
- **Strategic layer:** regions, routes, settlements, fortresses, factions, armies and political control across a wide map.
- **Local settlement layer:** detailed construction, household needs, production and population management for owned/nearby/relevant places.
- **Tactical layer:** focused battles or siege encounters on a local battlefield.

This model is PROPOSED, not locked. We need to decide whether all the layers share one zoomable world, use different scenes, or use a hybrid.

## Geography as gameplay

Candidate features from the user's vision:
- Sahyadri and other mountain ranges, hilltops and defensible passes.
- Rivers, bridges/fords and crossing points.
- Plateau farms, forests, grazing areas, roads and coastal trading centers.
- Terrain/weather affecting cultivation, travel speed, visibility, combat and siege endurance.
- Hill forts and settlements with different defensive and economic profiles.
- Routes where armies and slow supply trains can be intercepted.

Every geographical feature should support a real decision. Avoid making every terrain type a separate system if a small number of movement, visibility, production and defense modifiers can create the desired results.

## Historical framing

- Existing GDD baseline: Deccan around 1660.
- Current conversation: wider 1600–1700-era Indian setting and a long-range map aspiration.
- Exact campaign year, political boundaries, named figures, faction roster, settlement roster, and historical/alternate-history boundary are OPEN.

Candidate powers mentioned by the user include Deccan sultanates, Mughal authority, Maratha/Deccan local lords, Siddis, British, Dutch, Portuguese, French, Spanish and Arab-linked trading or political groups. Presence and role must be verified against the selected date and region; do not populate the game just because a power is familiar today.

## Content tiers — proposal

For manageable development, consider marking places as:
- **Playable-detail:** player-owned or locally contested settlements that use household/production/building simulation.
- **Strategic-detail:** AI-held places represented by a simpler aggregate state until the player interacts with them or they become strategically relevant.
- **Named landmark:** important historical location with defined strategic purpose and a lightweight state.

This could make a wide map possible without calculating every home and workshop at equal detail. It requires a test and explicit design decision.

## Historical accuracy policy

Maintain a research ledger with: claim, region/date, source, confidence, game interpretation, and whether the mechanic departs from history for playability. User-provided local knowledge should be captured as valuable research input but not silently represented as independently verified fact. See [research and decision log](12_decision_log.md).
