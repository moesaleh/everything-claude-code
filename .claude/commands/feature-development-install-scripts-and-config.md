---
name: feature-development-install-scripts-and-config
description: Workflow command scaffold for feature-development-install-scripts-and-config in everything-claude-code.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-install-scripts-and-config

Use this workflow when working on **feature-development-install-scripts-and-config** in `everything-claude-code`.

## Goal

Adds or enhances install-related features, including catalog/project config autodetection, by updating scripts and adding corresponding tests.

## Common Files

- `scripts/install-apply.js`
- `scripts/catalog.js`
- `scripts/ecc.js`
- `scripts/install-plan.js`
- `scripts/lib/install-manifests.js`
- `scripts/lib/install/config.js`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add JavaScript files under scripts/ (e.g., install-apply.js, catalog.js, install-plan.js, lib/install-manifests.js, lib/install/config.js).
- Add or update test files under tests/scripts/ and tests/lib/ to cover new install/config logic.
- Commit with a 'feat:' message describing the install/config enhancement.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.