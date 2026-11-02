# Development

Implement code, resources, data, and necessary documentation according to the current Plan. Read the [technical and style baseline](technical-baseline.md) before implementation. If the approach is insufficient to proceed, complete the necessary [Plan](plan.md) for the task first.

## Implement

- Preserve existing user edits and valid conventions; tie each change to the current task.
- Follow project and target-version vanilla implementation patterns, preserving system ownership and dependency direction.
- Verify APIs, signatures, events, and version differences against documentation and source; retain traceable evidence for important findings.
- Update applicable registration, resources, data, and documentation together, respecting the boundary between handwritten assets and generated output.
- Choose an implementation that meets current needs; new configuration, helpers, abstractions, or libraries require a concrete present use.
- Use existing project tools and commands. Keep temporary environment adjustments local to the current command or session, without changing unrelated host settings for troubleshooting.

Complete simple tasks directly and advance complex features through the capability slices in Plan. Add logging or state visibility for concrete diagnostic needs. A Debug Panel, fixed test world, unit tests, or GameTest are not mandatory deliverables for every iteration. See [Review](review.md) for default validation and player responsibilities.

## Handle discoveries during implementation

Fix ordinary implementation defects within the current authorization. Update Plan when only the implementation approach or sequence changes. For mechanism or architecture changes, explain the conflict, impact, and required decisions, then return to Design.

Check new user requests against the current scope. Keep unrelated improvements and future work as candidates. Increasing complexity does not itself authorize new dependencies, structural refactoring, or broader validation.

## Complete and hand off

Confirm that relevant code, resources, data, and documentation are synchronized, inspect the complete change, and enter Review. Reuse the existing Plan to record actual changes and necessary limitations; small edits need no separate phase report.

Development completion means the implementation is ready for inspection. Review reports structural, build, and startup results before handing gameplay testing to the player.
