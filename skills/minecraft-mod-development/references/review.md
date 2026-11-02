# Review

Compare the current Design or maintenance baseline, Plan, and actual changes to determine whether the result is ready for the player to try. Review includes actual runtime outcomes, with gameplay and experience evaluated through player testing and feedback.

## 1. Default checks

1. Read relevant design or maintenance contracts, the complete change, and necessary context. Check scope, behavior alignment, ownership, and obvious omissions.
2. Check consistency among affected code, resources, data, and dependencies. Verify APIs or behavior through documentation and source using the [technical and style baseline](technical-baseline.md).
3. Build using the project's existing commands.
4. Start the relevant client or server, confirm initialization completes without an immediate crash, and inspect related startup errors.
5. Summarize the results and provide a short player testing checklist.

A successful client startup requires evidence such as the main menu appearing or an unambiguous initialization-complete log. A server requires its startup-complete log. A running Gradle task or live process alone is insufficient. Confirm startup without entering a world to exercise mechanisms.

A standalone Review reports findings first; fixes follow user authorization. Do not expand default checks into exhaustive dedicated-server/multiplayer matrices, performance benchmarks, new test frameworks, or extensive screenshots and recordings. Scope specialized work when requested or needed to diagnose an actual problem.

Hand off once structure, build, and startup checks pass without related blockers. Repeat checks only when changes, failures, or unresolved concerns justify them. Manage running processes according to existing arrangements without terminating the user's pre-existing game instances.

## 2. Errors and environment blockers

Diagnose build or initialization errors caused by this implementation, fix them within authorization, and recheck affected parts. When environment or dependency limitations prevent checks, report actions taken, the specific gap, and what remains unverified, then hand off necessary build/startup steps. Never report an incomplete check as passed.

Base findings on evidence. Assess warnings by their relevance and actual impact on the current feature; their mere presence does not justify indefinite investigation.

## 3. Player gameplay testing

The player operates the game and tests mechanisms, UI, presentation, and experience by default. Use ComputerUse, game commands, or another control channel for gameplay testing only when the player explicitly requests it. Do not attempt automation before handing testing to the player.

For each item, give necessary preparation, actions, and observable expected results tied to the current change. Keep the checklist proportional to the feature; add directly relevant failure, cancellation, or relog cases only as needed. For example:

```markdown
## Player testing

- Preparation: Use this iteration's build and required prerequisites; include item-granting or feature-trigger commands when useful.
- Actions: Describe the entrypoint and main steps in order.
- Expected result: State what the player should observe.
- If something differs: Report the actions and actual result; provide relevant errors, logs, or screenshots when needed for diagnosis.
```

Do not require recordings or full reports by default. Ask for specific missing diagnostic information after receiving feedback.

## 4. Report and resume

Report structural checks, build, startup, and player testing separately, for example:

```text
Structural review: complete; no blockers found
Build: passed
Client startup: passed
Gameplay behavior and experience: awaiting player testing
```

This is a reporting example; use actual results. Pending player testing is neither an implementation failure nor runtime acceptance. Finish the current implementation turn while retaining the player's pending items.

Keep the following in the project's existing Plan or handoff record:

- Iteration scope and the corresponding Design or maintenance baseline.
- The build artifact or implementation location provided to the player; reference an existing commit when available, otherwise describe the uncommitted workspace state.
- Player testing items for this iteration.
- Received feedback, including what passed, failed, or remains untested.

On resumption, establish which implementation and steps the feedback concerns; ask only when ambiguous. Mark changed behavior for another player check instead of reusing an older build's conclusion. Retain feedback unaffected by the change.

Route implementation deviations to Development, technical approach changes to Plan, and mechanism or architecture issues to Design. For experience feedback, distinguish a deviation from the accepted Design from a new design request before routing it.
