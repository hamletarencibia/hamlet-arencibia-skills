---
name: changelog-writer
description: Maintain this package's temporary change notes and versioned changelog. Use when making meaningful package changes or preparing a version release.
---

# Changelog Writer

Keep unreleased work in `CHANGELOG-TEMP.MD` and released history in `CHANGELOG.MD`.

## Record current work

- Before recording a change, inspect `CHANGELOG-TEMP.MD`, `CHANGELOG.MD`, and `package.json`.
- Record each meaningful change in `CHANGELOG-TEMP.MD` with enough detail to explain the affected behavior, component, or documentation. Skip trivial formatting-only edits and duplicate notes.
- Do not record internal test-only changes, including test fixtures, assertions, mocks, snapshots, and test utilities. When tests accompany a user-facing or public API change, record the product change rather than the tests.
- Maintain `CHANGELOG-TEMP.MD` as a concise list of the current unreleased changes; do not add version headings there.
- Consolidate all refactoring and optimization work into exactly one line. Label it either `Code refactor:` or `Optimization:` and update that line as further related work is completed instead of adding another.

## Release a version

- Use the version currently declared in `package.json` as the release header.
- Create a `## <version>` header using that package version, then move the temporary change entries beneath it at the top of `CHANGELOG.MD`, immediately below its title. Do not move the temporary file's `# Current Changes` title. The newest version must always be first.
- Preserve every existing released version section and its content. Never replace or truncate `CHANGELOG.MD` while adding a release.
- Remove the temporary change entries, leaving the `# Current Changes` title in place, only after confirming that they were successfully added to the new version section.
- If there are no meaningful temporary entries, do not create an empty release section.

## Verification

- Confirm that the temporary notes remain intact for unreleased work.
- After a release, confirm the new version is the first version section, prior version sections remain unchanged, and the temporary file is empty.
