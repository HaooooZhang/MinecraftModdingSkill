# Design Output

Use only after Gate passes. Design Output converts confirmed Design into an engineering handoff; it does not reopen mechanism decisions.

## RoadMap

For each stage, record the goal, deliverable capability, system/prerequisite dependencies, parallel work, current versus `planned` scope, completion condition, next entry, and Test/Review scenarios. Prefer capability closures or vertical slices over a flat list of blocks, items, entities, or screens. A host-dependent extension may use “host loop + extension” as its route. RoadMap may reference `planned` items but never makes them hidden current prerequisites.

## Priority

Order current work using core-loop membership, prerequisite/blocking value, early risk exposure, architecture impact, vertical-slice value, player value, production cost, technical/compatibility risk, maintenance cost, and preservation of original behavior. A project may use:

- `P0`: required for the current closed loop;
- `P1`: core experience or key dependency;
- `P2`: important but non-blocking extension;
- `P3`: presentation, convenience, optimization, or low-risk polish.

Priority never promotes a `planned` item into current scope.

## Architecture Contract

The player/project owner chooses codebase topology, data-driven versus code-driven balance, registration style, and organization axis. Record the choice, reason, scope, and limits. Without confirmation, AI must not impose a universal `common / client / server` tree, create/remove Gradle modules, turn a single-loader project into a multi-loader project, change data-generation strategy, or reorganize an existing package tree.

Record the selected single/multi-loader and source-tree/module topology, existing-structure policy, organization axis (system/domain, responsibility, content type, platform, or hybrid), owners of registration/domain/network/datagen/resources/presentation/tests/integrations, runtime-side properties, platform/host boundaries, and the placement rule for a new class (system, module, owner, callers, dependencies, fixture).

Regardless of names, confirm that registration entrypoints do not own complex domain logic, domain systems do not depend on client presentation, network transports data without replacing domain ownership, integrations use public interfaces/events/adapters, platform APIs stay isolated, cross-system ownership is explicit, cycles have an explicit resolution, and generated versus hand-maintained resources are separated.

For Architectury or another abstraction, record actual modules, platform matrix, shared/platform code, isolation mechanism, missing-capability fallback, and `targeted` versus `verified` combinations. A single-loader project should not pre-build a platform layer for a hypothetical future.

## Completion

Output is complete when RoadMap, priority rationale, the player-approved Architecture Contract, next Plan, carried constraints/risks, Test/Review tasks, and `planned` re-entry conditions are recorded. If architecture cannot support the confirmed Design, start a new Design cycle instead of silently changing structure.
