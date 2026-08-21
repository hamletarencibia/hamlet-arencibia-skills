# Changelog Writer

A skill for maintaining a package's temporary change notes and released changelog consistently.

## What it does

The `changelog-writer` skill manages two changelog files:

- `CHANGELOG-TEMP.MD` — the concise list of meaningful changes that are not yet released.
- `CHANGELOG.MD` — the permanent, versioned history of released changes.

It is intended to be used whenever a meaningful package change is made or when preparing a new version release.

## How it works

### Recording changes

Before adding a change, the skill checks:

- `CHANGELOG-TEMP.MD`
- `CHANGELOG.MD`
- `package.json`

Meaningful changes are added to `CHANGELOG-TEMP.MD` with enough context to describe the affected behavior, component, API, or documentation.

The temporary file stays intentionally simple:

```md
# Current Changes

- Added support for ...
- Fixed ...
- Updated ...
```

There are no version headings in `CHANGELOG-TEMP.MD`.

### What should not be recorded

The skill skips:

- Trivial formatting-only changes.
- Duplicate entries.
- Internal test-only changes such as fixtures, assertions, mocks, snapshots, and test utilities.

When tests accompany a user-facing or public API change, the changelog records the actual product change rather than the tests themselves.

### Refactoring and optimization

All related refactoring or optimization work is consolidated into **exactly one line** in the temporary changelog.

Use one of these labels:

```md
- Code refactor: ...
```

or

```md
- Optimization: ...
```

As additional related work is completed, update that existing line instead of creating another entry.

## Releasing a version

When preparing a release, the skill uses the version declared in `package.json` as the release version.

The new section is added to the top of `CHANGELOG.MD`, immediately below its title:

```md
# Changelog

## 1.2.0

- Added support for ...
- Fixed ...

## 1.1.0

- Previous release changes...
```

The release process follows these rules:

1. Use the exact version from `package.json`.
2. Add the new version as the first version section.
3. Move the current temporary entries beneath that version heading.
4. Preserve every existing release section and its contents.
5. Never replace or truncate `CHANGELOG.MD` while creating a release.
6. Only clear the entries from `CHANGELOG-TEMP.MD` after confirming they were added successfully to the new release section.
7. Keep the `# Current Changes` title in `CHANGELOG-TEMP.MD`.
8. Do not create an empty release section when there are no meaningful temporary entries.

## Verification

After recording changes, verify that the temporary notes still contain the current unreleased work.

After a release, verify that:

- The new version is the first version section in `CHANGELOG.MD`.
- The previous version sections are still present and unchanged.
- All temporary entries were transferred successfully.
- `CHANGELOG-TEMP.MD` contains only its `# Current Changes` title and no unreleased entries.

## Suggested workflow

A typical workflow looks like this:

```text
Make a meaningful change
        ↓
Inspect CHANGELOG-TEMP.MD, CHANGELOG.MD, package.json
        ↓
Update CHANGELOG-TEMP.MD
        ↓
Continue development
        ↓
Prepare release
        ↓
Read version from package.json
        ↓
Create new version section in CHANGELOG.MD
        ↓
Verify the release was added correctly
        ↓
Clear temporary entries
        ↓
Verify CHANGELOG-TEMP.MD is empty
```

## Files expected by the skill

```text
project/
├── CHANGELOG-TEMP.MD
├── CHANGELOG.MD
├── package.json
└── ...
```

## Skill definition

The skill can be installed or referenced with the following metadata:

```yaml
---
name: changelog-writer
description: Maintain this package's temporary change notes and versioned changelog. Use when making meaningful package changes or preparing a version release.
---
```

## Design goals

The skill is designed to make changelog maintenance:

- **Consistent** — changes follow the same structure and rules.
- **Low-noise** — trivial and test-only changes do not clutter the release history.
- **Safe** — existing release history is preserved during releases.
- **Release-ready** — unreleased work is collected in one temporary file until a version is published.
- **Verifiable** — every release includes explicit checks to prevent lost or duplicated changelog entries.
