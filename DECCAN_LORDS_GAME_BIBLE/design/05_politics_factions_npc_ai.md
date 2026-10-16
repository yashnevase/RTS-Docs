# 05 — Politics, factions, companions and NPC decision-making

## Political fantasy

The player begins as a local hereditary lord in a hierarchy of overlapping clan, village, fort, regional, kingdom and imperial power. Authority is not merely a map color: it may depend on allegiance, revenue, military obligation, recognition, relationships, prestige, fear, family ties and a ruler's ability to protect subordinates.

The exact number and names of political levels are OPEN. The game should not force a single linear promotion path if the player can become a rival, mercenary or outlaw.

## Relationships

Candidate relationship dimensions:
- Personal relations / trust.
- Allegiance to current superior.
- Fear and estimate of military strength.
- Ambition and risk tolerance.
- Greed / material motivation.
- Reputation for keeping promises, generosity, cruelty or reliability.
- Kinship, clan ties and past events.
- Memory of a bounded set of recent meaningful actions.
- Knowledge confidence: what the NPC believes about the player and other lords.

Avoid duplicate stats that all mean “friendliness.” Each variable should have a distinct mechanical effect and visible explanation where possible.

## Political actions — candidate list

Gifts, tribute, requests for support, hiring service, treaties, alliance, non-aggression, military access, trade contracts, promises, betrayal, spying, rumor, bribery, protection, vassalage, rebellion, secession, surrender, succession or election by nobles, and recognition of a new ruler. Marriage, dynasty and succession scope need special treatment and may belong in a later version.

## Companion and governor ambition

The user wants companions with statistics who can be assigned to lead parties or take responsibility for territories and perhaps become allied lords/kings later. This is a major feature because delegated companions can change the scale of the world. V1 must define whether companions can only command parties or can independently govern and found higher political entities.

## Candidate AI decision architecture

**PROPOSED: use explainable, data-driven AI first.**
- Utility scoring ranks valid options based on goals, personality, resources, relations, threats, opportunity and expected payoff.
- A planner (for example, goal-oriented action planning) can assemble steps toward goals such as raising an army or capturing a pass.
- Tactical behavior trees/state machines handle immediate unit/army execution.
- Bounded randomness and seeded testing provide variation while keeping scenarios reproducible.
- A memory/state system records significant interactions and consequences.

ML is not rejected forever. It should only enter runtime decision-making when a specific measurable problem is defined, and its behavior can be tested, bounded and kept fair. ML might first assist with offline balance analysis, playtest clustering or content generation.

## Political hierarchy / player progression

Potential path: minor heir → recognized local lord → regional power/vassal or independent claimant → king/ruler of a realm → emperor or leader of a multi-king coalition. The user has suggested requiring a minimum number of holdings, forts, allied rulers and political recognition for higher status. All exact prerequisites, votes, titles, inheritance rules and consequences are OPEN.

## AI personality without chaos

Different lords can share the same algorithm but have different goals, fears, budgets, geography, allies, memories, military doctrine and risk preferences. Their actions should be driven by explainable state and constraints, not arbitrary hidden advantages. Randomness should select among plausible options, not replace planning.
