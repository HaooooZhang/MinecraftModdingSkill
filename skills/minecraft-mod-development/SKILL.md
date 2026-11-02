---
name: minecraft-mod-development
description: Plan, implement, and review Minecraft mod changes against an accepted Design or a clear maintenance baseline. Use for technical implementation planning, feature development, bug fixes, bounded ports, implementation review, and player-feedback follow-up. Return unresolved mechanism or architecture decisions to Design.
metadata:
  version: "0.1.0"
---

# Minecraft Mod Development

Turn an accepted Minecraft mod Design or a clear maintenance request into a concrete plan, implementation, and a result ready for the player to try. This Skill covers Plan, Development, and Review; Development corresponds to Develop in the existing workflow.

## Entry and stage routing

Inspect the request, repository, and existing materials to choose the entry stage. Read only the references needed for the current work.

- To create or revise an implementation plan, read [Plan](references/plan.md).
- To implement an accepted feature or fix a defect, read [Development](references/development.md). Fill any necessary planning gaps for the current task first.
- To inspect changes, check builds and startup, or process player feedback, read [Review](references/review.md). A standalone Review inspects and reports; fixes depend on the user's authorization.
- For API research, implementation choices, or code style during Plan and Development, read the shared [technical and style baseline](references/technical-baseline.md).

```text
Design Output / clear maintenance baseline
  -> Plan -> Development -> Review
  -> Player gameplay testing -> Feedback and routing
```

Resume from an existing Plan, implementation, or player feedback when appropriate. Complete only the requested stage when the user asks solely for Plan or Review. Stage routing does not switch Harness collaboration modes; when Harness Plan mode is active, follow its execution restrictions and output requirements.

## Establish execution context

Discover facts from the repository and available materials before asking the user for essential missing information or meaningful tradeoffs:

- The workspace, existing edits, comparable implementations, and their entrypoints.
- Relevant parts of the current Design, Gate, RoadMap, Plan, and Architecture Contract.
- Minecraft, loader, Java, host, prerequisites, and resolved dependency versions.
- Current scope, explicit exclusions, `planned` work, and names, IDs, APIs, or behavior that must be preserved.
- Existing build/startup evidence, the implementation version provided to the player, and their feedback.

New features start from the current Gate-approved Design Output. Clear bug fixes, local maintenance, and standalone Review may use a simplified entry based on the user's request, valid documentation, and existing implementation without completing an entire Design cycle. Surface conflicts between documentation and code; existing behavior is not automatically intended behavior.

## Shared boundaries and feedback routing

Preserve the accepted architecture, data-driven strategy, and project structure. Consult `planned` work only for necessary current constraints; keep it outside current implementation and dependencies.

| Finding | Action |
| --- | --- |
| Implementation defect; mechanism unchanged | Fix within authorization and recheck affected parts. |
| Implementation approach, task order, or file scope changes; mechanism and architecture unchanged | Revise Plan and continue. |
| Goals, triggers, states, key values, ownership, or cross-system contracts need new decisions | Return to Design, explain the impact, and rerun Gate as needed after revision. |
| A key technical fact is unresolved | Inspect documentation and source; record the specific gap and what it blocks if unresolved. |
| Environment or dependency blocker | Record completed checks and required conditions; use an accepted fallback or hand off. |
| Future feature or unrelated improvement | Keep it as a candidate until its scope is confirmed. |

Use `minecraft-mod-design` for mechanism or architecture questions when available. Otherwise, present the unresolved design decisions directly; another Skill installation is not a prerequisite for discussion.

## Default completion and handoff

Plan must directly guide implementation. After Development completes the current scope, Review checks structure, build, and startup on the relevant runtime side. Once those checks pass, provide a short player testing checklist and finish the current implementation turn.

Gameplay behavior, visuals, and experience are tested by the player by default. Operate the game for testing through ComputerUse or any other control channel only when the player explicitly requests it. Do not set up a new automated gameplay testing system by default.

Report build, startup, and gameplay results separately. Identify checks blocked by the environment, and leave player testing pending until feedback arrives. Reuse the project's Plan or handoff record to retain scope, build artifact or implementation location, player testing items, and feedback for continuation.
