# Establish Context

Use this reference at the start of every Design cycle. Establish Context does not design mechanisms; it identifies what is being designed, what is already known, and which questions should be asked next.

## Design type

Classify the current work as one or more of:

- whole-project design;
- module or mechanism refinement;
- design revision after new requirements/evidence;
- port/fidelity migration;
- audit or normalization of an existing design document.

If an existing design document already answers a question and remains valid, carry it forward as a fact. Ask about gaps and conflicts only.

Each Design type changes the evidence to read and the work permitted in this cycle:

| Design type | Read first | Do in this cycle | May skip |
| --- | --- | --- | --- |
| `whole-project` | project brief, existing docs, dependency and platform inventory | establish the project loop, module map, shared contracts, RoadMap, and next priority | deep per-content balancing and implementation details |
| `module-refinement` | parent Design, module docs, related system contracts | inherit or explicitly override the module's terms, boundaries, logic, and acceptance conditions | re-designing unaffected project areas |
| `revision` | current Design, change request, affected evidence and decisions | identify impacted contracts, revise them, and route consequences to dependent scopes | re-reading unrelated history |
| `port` | original design, original code/behavior, target-platform constraints | build the fidelity difference matrix and decide only confirmed migration deviations | inventing new gameplay or silently improving behavior |
| `document-audit` | claimed Design, source, builds, and dated decisions | reconcile facts, conflicts, missing fields, and stale claims | treating undocumented assumptions as decisions |

The selected type is an operating mode, not a descriptive label. Record its skipped branches and the condition that would reopen them.

## Mod classification

Record three independent dimensions:

1. **System role:** core content, non-core content, QoL, tool/API, compatibility, or optimization/low-level modification. Core describes how strongly content drives the main experience, not project size or system complexity.
2. **Gameplay:** choose one primary `Focus` (for example `tech` or `magic`) and any supporting gameplay tags, such as automation/production, combat, agriculture/cooking, ecology, exploration, creatures, bosses/hostiles, building/decor, survival, logistics/storage, transport, dimensions, biomes, structures, tools, weapons/gear, guides/information, economy, social, utility, or minigames. Both Focus and tags are presets rather than a closed list; add a more accurate value when needed.
3. **Theme:** choose one or more presentation directions such as technology, magic, adventure, horror, fantasy, nature, meme, modern, or historical. Themes may be extended or left empty; do not force a project into a preset.

“Port” is a project source/state, not a mod category. Record project scale separately from core status and system complexity.

## Source and existing basis

Record whether the project is new, a port, continuing development, a remake/refactor, or a host-dependent extension. Collect available design documents, source, release artifacts, running versions, screenshots/video, configuration, licenses, and build/runtime state.

For a port, request the original design and observed behavior before proposing changes. For a small host-dependent mod, identify the host loop, the added behavior, integration points, and fallback when the host is absent; do not require an invented independent core loop.

## Technical profile

Record facts, not implementation guesses:

- Minecraft, loader, mappings, Java/build versions;
- planned, in-development, and verified combinations;
- client, logical server, dedicated server, or both;
- required/optional host, prerequisite, integration, API, and abstraction-layer versions;
- network, configuration, resource-pack, save/world/chunk/player-data and migration boundaries;
- Architectury or similar abstraction modules, platform matrix, shared/platform differences, and unsupported capabilities.

Technical profile affects later questions but does not change the three mod-classification dimensions.

## Scope, users, constraints, and risk signals

Capture the current milestone (`v1`, `phase-1`, `mvp`, or an explicit module milestone), users and use scenarios, must-preserve behavior, allowed changes, time/team/tool/material limits, licensing constraints, and signals such as low-level edits, world generation, pathfinding, rendering, cross-mod integration, migration, networking, or performance sensitivity.

Keep `exploration`, `out-of-scope`, and `planned` separate from current scope. `planned` is future work and is not read into current Design except for necessary compatibility constraints.

## Question routing and completion

Choose question density and challenge level from project scale, risk, user expertise, and the Design type. The context step is complete when the current Design type, classification, source, environment, existing basis, scope, constraints, risks, user preference, and next question domains are recorded; unresolved items are labelled rather than guessed.
