# Status, Scope, and Design Structure

Use this reference when recording project status, live design documents, scope labels, or design-folder organization.

## Separate status dimensions

Keep these questions separate:

- **Project state:** whether the project is active, paused, ended, or archived;
- **Design type:** whole design, module/mechanism design, revision, port comparison, or existing-document audit;
- **Design maturity:** `not-started`, `in-design`, `awaiting-review`, `ready`, `needs-revision`, `on-hold`, or `deprecated`;
- **Workflow position:** Design, Plan, Develop, or Review;
- **Implementation/verification:** `implemented`, `tested`, and `stable` are not design-maturity states;
- **Scope/milestone:** current milestone (`v1`, `phase-1`, `mvp`, or module milestone), `exploration`, `out-of-scope`, and `planned`.

Large projects may have modules at different workflow positions while the project remains active. Core status, scale, and system complexity are not status values.

`planned` means future work excluded from the current Design. Keep only its direction, value, dependencies, necessary compatibility constraints, trigger, and conditions for re-entering Design. Do not write full terms, mechanisms, numbers, UI, or implementation plans for it. RoadMap may link it, but Plan, Develop, and Gate must not treat it as a current requirement or hidden prerequisite. Promotion removes `planned` and starts a new Design cycle.

`v1` is a current deliverable milestone, not a Design document version and not a compound status label. Use milestone, priority, behavior, and acceptance fields to express required versus optional current work.

## Scope inheritance

Use the hierarchy `project -> system -> mechanism -> content item` when a project needs multiple Design levels. A child scope inherits still-valid parent decisions unless it records a relationship of `local`, `override`, or `unknown` for that item. An `override` must include its reason, affected scopes, and whether it reopens a parent Design. Silent changes to parent goals, loops, terms, units, boundaries, or cross-system contracts are invalid.

## Live design documents

An initial Design need not finish every future module. Establish project boundaries, shared terms, module map, preliminary architecture, dependencies, RoadMap, and the next priority module first. Each module can carry its own snapshot, confirmed facts, inferences, open questions, dependencies, maturity, workflow position, and change history.

## Logical design-folder roles

Small projects may use one document. Larger projects may use a `design/` folder whose roles are logical, not mandatory filenames or extensions:

```text
design/
├── <entry>          # metadata, current status, navigation
├── context/         # Establish Context snapshots and source index
├── glossary/        # terms and mechanism table
├── content/         # blocks, items, entities, recipes, etc.
├── scope/           # current milestone, options, exclusions
├── future/          # `planned` directions (normally skipped)
├── architecture/   # system, runtime-side, data and network boundaries
├── roadmap/         # Gate-approved RoadMap and priority
├── systems/        # system map and per-system documents
├── decisions/      # important decisions and reasons
├── evidence/       # prototypes, observations, benchmarks, validation index
└── archive/        # superseded snapshots
```

A role may be a file, folder, table, diagram, or mixed resource. Keep Plan, Develop, Review, and test reports as linked deliverables rather than Design body; preserve history in `archive/` instead of overwriting decisions.

## Technical coverage levels

Select depth from system role, gameplay, Design type, scale, and risk:

- `minimal`: mechanism, boundaries, and player result can be described;
- `targeted`: required technical constraints for the current classification/module;
- `full`: architecture, performance, compatibility, data, network, migration, and rollback.

Early whole-project Design often uses `minimal + targeted`. Module development needs the relevant `targeted` coverage. Optimization/low-level changes, complex networking, migration, and high-risk compatibility require `full`. Unknown APIs that require code, prototypes, or runtime evidence become `evidence-task`, not invented facts.

## External references and skills

Use available grilling, game-design, Minecraft Wiki, loader, host, API, and modding references when their branch applies. External Skills can provide questioning or sparring methods, but the current project Skill owns scope, status, Minecraft boundaries, and recording rules. Do not copy an external framework's default categories if they conflict with the player's choices.
