# Grill / Design

Use this reference for the core clarification loop. Grill discovers problems; Design organizes confirmed answers. They may alternate repeatedly.

## Fact Map and Design Pins

Classify each statement as `user-decision`, `fact`, `observation`, `inference`, `assumption`, `unknown`, `contradiction`, `deferred`, or `evidence-task`. Keep source, version, confidence, and affected scope where useful. Design Pins are decisions that constrain downstream work (goal, terminology, units, ownership, compatibility, preservation rules, or boundaries).

Do not turn examples, suggestions, references, or Brainstorm candidates into facts.

## Scope hierarchy and inheritance

Design scope may be nested as:

```text
project -> system -> mechanism -> content item
```

Use only the levels the project needs. A decorative block may be designed directly as a content item; a technology network may require all four levels. A child scope inherits still-valid parent decisions by default. Mark each inherited decision as `inherited`, `local`, `override`, or `unknown`.

An `override` must state its reason, affected decisions and downstream scopes, and whether a new system- or project-level Design cycle is required. A child scope must not silently change a parent goal, core loop, term, resource unit, system boundary, or cross-system contract.

## Unknown routing

Every unresolved item must be routed to exactly one outcome:

- `question`: ask the user in the current Grill / Design loop;
- `evidence-task`: collect source, code, or runtime evidence before deciding;
- `deferred`: keep outside the current scope with an owner stage and re-entry condition;
- `out-of-scope`: explicitly exclude it from this Design.

Do not leave an unclassified unknown in a Gate-ready document.

## Dependency frontier

Maintain a frontier of the next questions whose prerequisites are known:

```text
goal/player behavior
  -> loop and failure/reward
  -> terms and mechanisms
  -> content and system boundaries
  -> logic and preliminary architecture
  -> technical, compatibility, and production constraints
```

Ask one question, a small batch, or a dense frontier according to the context profile. Resolve prerequisites before downstream details.

## Required design records

For the current scope, build or update:

- terminology/mechanism table: user name, English name, stable ID, type, definition, includes/excludes, relationships, status, source;
- content list: blocks, items, entities, effects, recipes, resources, structures, and other applicable units;
- goal and loop: `goal -> action -> cost/risk -> result -> reward -> next goal`;
- system map: purpose, owns/does-not-own, inputs, outputs, states/transitions, triggers, dependencies, persistence, feedback, client/server edge, and test target;
- logic chain, state diagram, sequence, or data-flow view;
- current scope, exclusions, `exploration`, `out-of-scope`, and `planned` boundaries;
- preliminary architecture and integration contracts.

Mechanism names must distinguish concepts such as a definition, runtime instance, entry, type, effect, system, and presentation. Do not use one vague name such as “effect” or “dialogue” for several different objects.

## Core loop and system fit

Large content mods need player goals, repeated actions, costs/risks, results, rewards, and the next goal. Small extensions may state “host loop + extension behavior.” Identify what the mod adds, what it reuses, and what disappears if a mechanism is removed.

Split systems by responsibility, state, ownership, and dependencies rather than by arbitrary package names. Every system should expose its inputs, outputs, state, triggers, failure/exception paths, persistence, side boundaries, and relationships to other systems.

## Brainstorm boundary

Brainstorm is optional and normally brief. If used, separate **current omissions** from **future plans**. Current omissions return here for confirmation or become explicit evidence/exclusion decisions. Future plans go to Future Plan as `planned` with value, dependencies, trigger conditions, and re-entry conditions.

**Hard rule:** without explicit user permission, do not write a Brainstorm candidate, assumption, alternative, or idea into confirmed Design text, tables, architecture, RoadMap, Plan, or any current-scope artifact. A permitted candidate still returns here if it changes a goal, core loop, term, unit, system boundary, or cross-system contract.

## Ports and existing designs

For ports, maintain a difference matrix with original design, observed original behavior, target-platform limits, migration strategy, and evidence. Label each row `design-defined`, `code-observed`, `conflict`, or `requires-user-decision`. Preserve behavior by default; record and request confirmation for every deviation. For existing documents, distinguish current facts from stale, contradictory, or undocumented claims.

## Completion

Leave Grill / Design only when current-scope mechanisms, terms, content, boundaries, logic, dependencies, and open items are explicit enough for Feasibility Review. Technical APIs may remain unknown; mechanism rules may not be left for Plan or Develop to invent.
