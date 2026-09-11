# `tech` Focus

This folder contains the reference branch for `Focus: tech`. Read this index when the project has technology-oriented systems such as automation, production lines, logistics, machines, energy, or processing. Future Focus branches such as `magic/` should live beside `tech/` under `references/focus/`.

It is a question and evidence map, not a default design.

## Energy and numbers

Identify the driving unit: FE/RF, Create stress/rotation/torque, heat/pressure/steam/fuel, redstone/environment, or a custom resource. If a host or prerequisite exists, use its units and interface conventions as the baseline.

Always separate:

```text
capacity != input rate != output rate != per-operation cost != processing time
```

Ask about storage, transfer, conversion/loss, generation, consumption, throughput, upgrade curve, infinite loops, and whether prerequisite values constrain the design. Produce project-specific tables or formulas only after the relevant units are known.

## Capability and logistics graph

For each transferable capability (energy, item, fluid, heat, pressure, stress, redstone, control/data, or custom resource), identify producer, storage/buffer, transport, consumer, push/pull semantics, face/port permissions, capacity, throughput, discovery/update/disconnect, chunk unload/reload, and compatibility with funnels/pipes/cables/other mods.

```text
producer -> storage/buffer -> transport -> consumer -> output
```

## Functional block questions

Use the three prompts from [“从熔炉科技到规则驱动，如何设计一个功能方块？”](https://myumoon.ink/2026/08/28/furnace-tech/):

- **What can I do?** Why does the player need it? Is it a new capability or an improvement? What phase, frequency, automation role, and system position does it have? What is lost if it is removed?
- **How do I do it?** What are input, rules, process, output, player decisions, automation, batching, complexity, and feedback?
- **How did I do?** Can the player read progress, bottlenecks, failures, output, efficiency, and the result of optimization?

Record the block's lifecycle from first use through repetition, automation, upgrading, and replacement. Do not reduce the design to a recipe JSON.

## Complete technology system

“Complete” means the declared technology experience closes; it does not require every mod to own power generation, logistics, machines, and automation. A host-dependent extension may explicitly rely on host systems.

Map:

- resource chain: raw -> primary processing -> intermediates -> components -> uses;
- capability chain: generation -> storage -> transport -> consumption -> result;
- progression: discover/acquire -> unlock -> build -> improve -> automate -> expand/new goal;
- machine roles: unlock, improve efficiency/yield, transform, automate, transport/control, or add meaningful decisions;
- player control and feedback: filters, priority, redstone, capacity, bottlenecks, guide/JEI/REI information.

Check source and sink for intermediate products, deadlocks, obsolete machines, late-game outlets, and whether machines are only reskinned tiers.

## Recipes and conventions

Review recipe purpose, alternative routes, namespace, conditions/groups, uniqueness, duplication loops, by-products, tags, containers, redstone, drops, BlockEntity persistence, menus, datagen, resources, creative access, guide integration, and missing-integration fallback. Deviations from vanilla/host convention require a stated design reason.

## Conditional checks and failure patterns

Enable scale checks for throughput, buffers, chunk boundaries, multiplayer networks, replication, and manual-to-automation transition. Watch for: every machine being a faster furnace, meaningless intermediate steps, energy with no gameplay role, unbalanced production/consumption, invisible bottlenecks, excessive manual confirmation, obsolete upgrades, no late-game sinks, free duplication loops, and missing state/failure feedback.

Use `Focus: tech` in Establish Context to select questions, in Grill / Design to form tables and graphs, in Feasibility Review to check capability and conventions, and in Test / Review to define numerical/runtime/player-experience verification.

## Focus-specific cases

Add future technology cases as focused files or subfolders under `references/focus/tech/`. Each case should state its scope, source, version, license, retrieval date, applicable questions, useful patterns, counterexamples, and the Design/Feasibility checks it informs.
