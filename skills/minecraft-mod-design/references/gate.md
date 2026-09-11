# Design Gate

Gate is the final completeness check inside Design. It asks whether the current scope is clear enough to hand to Plan.

## Inputs

Read the current Design snapshot, scope/milestone, Fact Map, terminology and content records, systems and logic, preliminary architecture, Feasibility Review, Brainstorm routing, unknowns, deferrals, degradation, and Test/Review handoff. Unapproved Brainstorm candidates and detailed `planned` content are outside the Gate input.

## Checklist

- goals, users, scenarios, scope, exclusions, and milestone are explicit;
- mechanisms have names, IDs, boundaries, triggers, states, results, feedback, and failure paths;
- terms, content lists, and system ownership are sufficient;
- systems are partitioned by responsibility, state, ownership, and dependencies rather than left as an implicit collection of mechanisms;
- child-scope inheritance, local decisions, overrides, and unknown relationships are recorded where scopes are nested;
- core or host-extension loop closes;
- dependencies, inputs/outputs, persistence, network, data, and runtime-side boundaries are clear;
- environment and prerequisite conclusions are recorded;
- applicable vanilla/host conventions, tags, recipe uniqueness, and content-family boundaries have no unresolved omission;
- no current item silently depends on `planned` work;
- Feasibility blockers are resolved, returned, explicitly deferred, or degraded;
- every current item can become a Plan task with order, dependencies, and acceptance conditions;
- later Test/Review scenarios and expected evidence are listed;
- Brainstorm candidates have not become requirements.
- every unresolved item has exactly one route: `question`, `evidence-task`, `deferred`, or `out-of-scope`;

Do not require final code structure, every implementation API, final balance, or runtime evidence. Do require that Plan and Develop will not have to invent mechanism rules, ownership, or critical contracts.

## Results

- `pass`: ready for Design Output and Plan;
- `pass-with-notes`: ready, with constraints, risks, prerequisites, and validation tasks carried forward;
- `fail`: return to the responsible Grill / Design or Feasibility step;
- `blocked`: wait for user decision, source, prerequisite, or external evidence.

`pass-with-notes` cannot conceal a missing goal, trigger, state, ownership, or cross-system contract.

## Record and completion

Record scope, Design snapshot, date, result, passed checks, non-blocking open items, Plan constraints, Test/Review tasks, and return/blocking reason. Gate is complete only when the result is explicit and the next entry is named. A failed Gate keeps its record and is rerun after revision.
