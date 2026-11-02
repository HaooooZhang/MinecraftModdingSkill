# Plan

Translate the accepted mechanisms for this iteration into implementation choices and preparation. Read the current Design or maintenance baseline, relevant Architecture Contract, RoadMap stage, and known constraints. Establish implementation facts using the [technical and style baseline](technical-baseline.md).

## 1. Explore before clarifying

Inspect entrypoints, comparable implementations, dependencies, data, and resources to identify what can be reused. Resolve discoverable questions through the repository, documentation, and source.

Establish the goal, completion criteria, scope, and important tradeoffs. Ask only when a missing decision affects the approach or result; inherit still-valid design decisions. Return mechanism gaps to Design rather than filling them with planning assumptions.

## 2. Define the implementation approach

Cover the parts relevant to the current mechanisms:

- Entry points, owning systems, callers, and dependency direction.
- Registration, events, commands, interactions, or tick integration.
- Data definitions, parsing, validation, configuration, and reload.
- State ownership, lifecycle, persistence, and cleanup.
- Client/server responsibilities and necessary network synchronization.
- Placement of UI, input, presentation, and feedback code.
- Required resources, data generation, tags, recipes, and related content.
- Host and third-party API integration, isolation, and accepted behavior when absent.

Identify existing implementations to retain and explain necessary technical choices. Choose directory layout, Datagen, Mixin, abstraction layers, and libraries according to project conditions and the Architecture Contract, rather than imposing a generic scaffold.

## 3. Sequence tasks and preparation

Organize work by behavior or subsystem. Split complex features into capability slices the player can try; a simple change may need only one task.

For each task, state its purpose, implementation approach, prerequisites, completion criteria, and player testing entrypoint. Name file paths only when placement affects ownership or could cause an incorrect edit; a file-by-file inventory is unnecessary. Specify interfaces and sequencing for cross-system work. Parallel task relationships do not authorize multiple agents by themselves.

List dependencies, assets, and information actually missing. Resolve unknown APIs or behavior that affect the approach, or explicitly mark them as blockers. Schedule a minimal prototype only when a concrete question requires one. Limit risks, fallbacks, and recovery steps to those relevant to the task.

## 4. Complete and hand off

The plan must be ready for another implementer without reopening goals, ownership, key interfaces, or the implementation approach. Ordinary internal choices, such as local variable names, can remain for Development.

Keep the plan proportional to the task, with the minimum detail needed to prevent concrete implementation mistakes. Use the following structure where helpful, omitting empty sections:

```markdown
# <Implementation plan title>

## Summary

<Design or maintenance baseline, capability, and scope>

## Implementation changes

<Concrete approach, interfaces, dependencies, and sequence by behavior or system>

## Validation and player testing

<Agent structure/build/startup checks, plus player actions and expected results>

## Assumptions and open decisions

<Necessary assumptions, missing facts, and blockers; omit when absent>
```

Expand schemas, wire formats, migrations, fallback policies, or validation rules only when the task requires them. Plan does not require agent gameplay testing, exhaustive environment matrices, or new test frameworks.

Follow the required format and restrictions when Harness Plan mode is active; an ordinary planning request does not switch modes. Stop after delivering the plan when planning is all the user requested. When implementation is already authorized, continue to Development as permitted by the active mode.
