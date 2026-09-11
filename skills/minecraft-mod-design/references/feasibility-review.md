# Feasibility Review

Feasibility Review validates the confirmed Design; it is not a second Design and not a runtime test.

## Questions

### Logic and mechanics

Check that the declared loop closes; goals, actions, costs/risks, results, rewards, and next goals connect; inputs/outputs/resources/states agree; success, failure, cancel, exception, and boundary paths have exits; systems have no hidden prerequisites or impossible states; progression, rewards, and costs do not create deadlocks, dead zones, or self-negating rules; and the mechanism supplies the intended decisions, changes, risk, reward, or expression rather than only extra clicks. If the declared design cannot support its goal, return it to Grill / Design.

### Technical capability and prerequisites

Ask only whether the current Minecraft/loader/version, repository, host, prerequisite, API, client/server side, and platform abstraction provide the required capability. A missing required library (for example, GeckoLib for a chosen animation approach) is a feasibility condition. Detailed class structure, code organization, and implementation order belong to Plan.

Use conclusions such as `feasible`, `feasible-with-prerequisite`, `insufficient-information`, `blocked`, and `deferred`, with a reason and affected scope.

### Vanilla and host conventions

Check content-family completeness, tags, recipe uniqueness, namespaces, registration/resources/data roles, drops, tools, redstone, containers, menus, persistence, worldgen, creative access, guide/JEI/REI integration, and missing-integration fallback. A deviation is acceptable only with a stated design reason.

### Conditional branches

Enable compatibility, port fidelity, production capacity, maintenance, performance/scale, network/save/data, and licensing checks only when the current project needs them. Optimization and low-level changes require explicit impact, target, risk, and rollback direction, while actual benchmarks remain Test/Review work.

## Evidence handoff

Record what later Test / Review must prove: build, launch, dedicated server, multiplayer, migration, performance, numerical behavior, or player experience. Do not claim those results during Feasibility Review. Distinguish a logical blocker (return to Design), a missing prerequisite (user/Plan decision), an evidence task (later validation), and a consciously deferred item.

## Completion

The review is complete when each applicable dimension has a reasoned conclusion, blockers have an owner and next action, convention gaps are handled, and later validation tasks are listed. It may recommend Gate; it does not pass Gate itself.
