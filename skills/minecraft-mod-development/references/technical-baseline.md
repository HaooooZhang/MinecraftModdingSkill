# Technical and Style Baseline

During Plan preparation and before Development, read existing code, relevant documentation, and source for the current problem. Ground the approach in verifiable project facts, keeping research proportional to the task.

## Implementation and style

1. Read comparable repository features and their call chains first. Preserve still-valid ownership, naming, registration, data handling, error handling, and code style.
2. Where the repository has no corresponding pattern, use vanilla Minecraft implementation and style for the target version, accounting for the loader's actual lifecycle and extension points.
3. Understand why project conventions differ from vanilla. Respect accepted conventions; fix defects within authorization and return mechanism or architecture changes to the appropriate decision stage.

Reuse mechanisms needed now rather than building extension layers for hypothetical features. Explain concrete problems with existing structure without reorganizing unrelated code as part of the task.

## Documentation and source

Read relevant official documentation for the target version and public host/dependency documentation to understand contracts and recommended integration. Wherever possible, verify key facts against source matching the version actually used by the project.

Check class and method signatures, event timing, runtime side, lifecycle, data formats, and semantics that affect the approach. Prefer the project's resolved dependencies, matching sources.jar files, or the corresponding version/commit. Account for loader patches when interpreting vanilla source.

If source is unavailable, inspect class signatures or decompile where licensing and tools permit, identifying the source type and limitations. Available MCP tools, indexes, or IDEs may assist research; verify the version and surrounding context of their results without assuming a particular tool is installed.

Community examples and other mods are supporting references, not proof that an API is available in the current version. Inspecting source and copying code are separate actions; follow applicable licenses when citing or reusing third-party material.

## Findings and traceability

Keep enough evidence to relocate important findings: documentation URLs and applicable versions, or dependency coordinates/source versions and class/method locations. Reuse task records instead of creating a separate report for every ordinary call.

Documentation describes public contracts; source reveals the inspected version's implementation. Record conflicts and assess their impact. Mark unverified findings as inferences or open evidence tasks, resolving those that affect the approach before proceeding. Do not invent APIs or present another version's implementation as a current fact.

Source inspection, compilation, and startup each support only their respective conclusions; they do not replace player testing of gameplay and experience. If source cannot be obtained, state that limitation and decide whether it blocks progress. Avoid indefinite research solely to satisfy a reading formality.
