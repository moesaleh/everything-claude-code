---
name: feature-development-ecc2-module
description: Workflow command scaffold for feature-development-ecc2-module in everything-claude-code.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-ecc2-module

Use this workflow when working on **feature-development-ecc2-module** in `everything-claude-code`.

## Goal

Implements a new feature or enhancement in the ecc2 Rust module, typically involving dashboard/UI or session management improvements.

## Common Files

- `ecc2/src/session/manager.rs`
- `ecc2/src/tui/dashboard.rs`
- `ecc2/src/session/store.rs`
- `ecc2/src/session/mod.rs`
- `ecc2/src/session/output.rs`
- `ecc2/src/session/runtime.rs`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add Rust source files under ecc2/src/, often touching session/manager.rs, tui/dashboard.rs, and related files.
- Update or add supporting modules (e.g., config/mod.rs, session/store.rs, tui/widgets.rs).
- Commit with a 'feat(ecc2): ...' message describing the feature.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.