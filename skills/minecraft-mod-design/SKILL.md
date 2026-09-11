---
name: minecraft-mod-design
description: Guide Minecraft mod or mod-module design from context and mechanism clarification through feasibility, Gate, RoadMap, priority, and a player-approved architecture handoff. Use when starting a mod, refining a system, auditing an existing design, or planning a port; do not use for implementation-only tasks that already have an accepted Design and Plan.
---

# Minecraft Mod Design

Use this Skill to turn an ambiguous Minecraft mod idea into a bounded, reviewable Design that can safely enter Plan. It supports new mods, host-dependent extensions, ports, revisions, and module-level design. Adjust depth to the mod's system role, gameplay Focus (for example `tech` or `magic`), gameplay tags, theme, source, scale, and current stage.

## Operating contract

Run the internal workflow in order, allowing explicit returns to earlier steps:

```text
Establish Context
  -> Grill / Design (loop)
  -> Brainstorm (optional)
  -> Feasibility Review
  -> Gate
  -> Design Output
  -> Plan
```

Read [references/establish-context.md](references/establish-context.md) when starting or re-entering a Design cycle. Read [references/grill-design.md](references/grill-design.md) during mechanism clarification. Read [references/feasibility-review.md](references/feasibility-review.md) for the feasibility branch, [references/gate.md](references/gate.md) at the final completeness check, and [references/design-output.md](references/design-output.md) after Gate passes. Read [references/status-and-structure.md](references/status-and-structure.md) when recording scope/status or choosing a live design structure. Read matching Reference Focus branches under `references/focus/` when they exist: for example, [references/focus/tech/index.md](references/focus/tech/index.md) for technology and `references/focus/magic/` for magic. Do not load unrelated Focus branches.

### 1. Establish Context

Identify the Design type: whole project, module/mechanism refinement, revision, port, or existing-document audit. Record the mod's system role, gameplay Focus and tags, theme, project source, host/dependencies/integrations, target Minecraft/loader/platforms, client/server boundary, existing documents/code/builds, current scope, constraints, and risk signals. Gameplay and Theme values are extensible. Treat existing confirmed documentation as facts; ask only about gaps or conflicts. Choose an appropriate question density and technical depth.

### 2. Grill / Design

Grill exposes undefined terms, assumptions, contradictions, boundaries, and decisions. Design organizes confirmed answers into:

- precise terms, stable IDs, mechanism/content tables, and content lists;
- project -> system -> mechanism -> content-item scope boundaries, with explicit inheritance or override records;
- goals, player actions, core loop or host-loop extension;
- system boundaries, ownership, inputs/outputs, states, triggers, failure paths, and feedback;
- logic chains, dependencies, preliminary architecture, and client/server, data, network, and save boundaries;
- unknowns routed as a question, evidence task, deferred item, or explicit out-of-scope decision;
- current scope, exclusions, and `planned` future work.

Keep mechanism definitions precise even when implementation APIs remain unknown. Route evidence-dependent questions as `evidence-task` instead of inventing facts. For ports, preserve the original design and behavior by default and record every deviation for confirmation.

### 3. Brainstorm (optional)

Skip or keep this step brief unless the user requests ideation, the Design has visible omissions or competing alternatives, the project's scale warrants exploration, or Feasibility Review sends a question back for exploration. Split every candidate into **current omission** or **future plan**. Current omissions return to Grill / Design or become an explicitly handled evidence/exclusion item. Future ideas go to Future Plan as `planned` with value, dependencies, trigger conditions, and re-entry conditions.

**Hard rule:** without explicit user permission, never write a Brainstorm candidate, assumption, alternative, or idea into confirmed Design text, terminology/content/system tables, architecture, RoadMap, Plan, or another current-scope artifact. Keep it clearly labelled in discussion until it is routed and authorized.

### 4. Feasibility Review

Review the confirmed Design, not unapproved ideas. Check logical/mechanism viability, technical capability and prerequisites, Minecraft/host conventions, and only the compatibility, porting, production, maintenance, scale, or performance branches that apply. Determine whether the current Minecraft/repository/dependencies can provide the required capability; do not decide detailed class structure or implementation order here. Record later Test/Review validation tasks without executing runtime tests in this step. Return mechanism gaps to Grill / Design.

### 5. Gate

Gate is the final Design completeness check: current goals and boundaries, mechanism contracts, system ownership/dependencies, environment/prerequisites, convention coverage, absence of hidden `planned` dependencies, resolved Feasibility blockers, and Plan-ready acceptance conditions. Use `pass`, `pass-with-notes`, `fail`, or `blocked`. `pass-with-notes` cannot hide a rule that Plan or Develop would have to invent. See [references/gate.md](references/gate.md).

### 6. Design Output

Only after Gate passes, produce RoadMap, priority, and a project-specific Architecture Contract. The player/project owner chooses codebase topology, data-driven versus code-driven balance, module/package structure, and whether a multi-loader abstraction is warranted. Do not impose a universal `common/client/server` tree, create Gradle modules, change data-driven strategy, or reorganize an existing repository without confirmation. See [references/design-output.md](references/design-output.md).

## Scope and status rules

- Keep current scope separate from `planned`; planned details are not read into current Design except for necessary compatibility constraints.
- Use `exploration` for undecided candidates and `out-of-scope` for explicit exclusions.
- `v1`, `phase-1`, or `mvp` are milestones, not Design document versions or compound status labels.
- Design status (`not-started`, `in-design`, `awaiting-review`, `ready`, `needs-revision`, `on-hold`, `deprecated`) is separate from implementation/test status.
- Do not treat a reference, suggestion, or inferred API fact as a user decision.

## Completion

Finish only when the current scope has a usable context snapshot, precise mechanism/content records, system and logic boundaries, applicable feasibility conclusions, a Gate result, and—when Gate passes—a RoadMap, priority rationale, and player-approved Architecture Contract. Preserve unresolved items with an owner stage and next action; never silently fill them during Plan or Develop.
