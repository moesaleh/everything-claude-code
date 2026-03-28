```markdown
# everything-claude-code Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute effectively to the `everything-claude-code` repository, a JavaScript-based project (with some Rust components) focused on automation scripts, install/config management, hooks, and session/dashboard features. You'll learn the project's coding conventions, commit patterns, and how to follow the main development workflows, including feature development, bugfixing, CI updates, and documentation.

---

## Coding Conventions

**File Naming**
- Use `camelCase` for JavaScript files.
  - Example: `installApply.js`, `sessionManager.js`

**Import Style**
- Use relative imports.
  - Example:
    ```js
    const utils = require('../lib/utils');
    import { applyInstall } from './install-apply.js';
    ```

**Export Style**
- Mixed: both CommonJS (`module.exports`) and ES module (`export`) styles are present.
  - Example (CommonJS):
    ```js
    module.exports = function runSession() { ... };
    ```
  - Example (ES module):
    ```js
    export function applyInstall(config) { ... }
    ```

**Commit Messages**
- Use [Conventional Commits](https://www.conventionalcommits.org/).
- Prefixes: `fix`, `feat`, `docs`, `chore(deps)`, etc.
  - Example: `feat: add autodetection for project config`
  - Example: `fix(hooks): guard against missing session`

---

## Workflows

### Feature Development: ECC2 Module

**Trigger:** When you want to add or enhance features in the `ecc2` Rust agent/session/dashboard system.  
**Command:** `/new-ecc2-feature`

1. Edit or add Rust source files under `ecc2/src/`, such as `session/manager.rs`, `tui/dashboard.rs`.
2. Update or add supporting modules (e.g., `config/mod.rs`, `session/store.rs`, `tui/widgets.rs`).
3. Commit with a message like `feat(ecc2): [describe feature]`.

**Example:**
```sh
# Edit ecc2/src/session/manager.rs
git add ecc2/src/session/manager.rs
git commit -m "feat(ecc2): add session timeout support"
```

---

### Feature Development: Install Scripts and Config

**Trigger:** When you want to add or enhance install/config logic or autodetection.  
**Command:** `/new-install-feature`

1. Edit or add JS files in `scripts/` (e.g., `install-apply.js`, `catalog.js`).
2. Add/update tests in `tests/scripts/` and `tests/lib/`.
3. Commit with a message like `feat: [describe install/config enhancement]`.

**Example:**
```sh
# Edit scripts/install-apply.js and add tests/lib/install-config.test.js
git add scripts/install-apply.js tests/lib/install-config.test.js
git commit -m "feat: autodetect install manifest from project root"
```

---

### Add or Update Hook

**Trigger:** When you want to add a new hook or update hook logic (e.g., desktop notifications).  
**Command:** `/new-hook`

1. Edit/add JS files in `scripts/hooks/` (e.g., `desktop-notify.js`).
2. Update `hooks/hooks.json` and `hooks/README.md`.
3. Add/update tests in `tests/hooks/` and `tests/scripts/`.
4. Commit with `feat:` or `fix:` referencing hooks.

**Example:**
```sh
# Add scripts/hooks/desktop-notify.js, update hooks.json, add test
git add scripts/hooks/desktop-notify.js hooks/hooks.json tests/hooks/hooks.test.js
git commit -m "feat(hooks): add desktop notification hook"
```

---

### CI Config Update

**Trigger:** When you need to fix or enhance CI workflows (e.g., for new validation logic).  
**Command:** `/update-ci`

1. Edit workflow YAML files in `.github/workflows/` (e.g., `ci.yml`).
2. Commit with `fix(ci):` or similar.

**Example:**
```sh
git add .github/workflows/ci.yml
git commit -m "fix(ci): add node 20 to test matrix"
```

---

### Dependency Bump

**Trigger:** When a dependency needs updating for security, compatibility, or features.  
**Command:** `/bump-dependency`

1. Update versions in `package-lock.json`, `yarn.lock`, `Cargo.lock`, `package.json`, or `Cargo.toml`.
2. Commit with `chore(deps):` or `chore(deps-dev):`.

**Example:**
```sh
npm install some-package@latest
git add package.json package-lock.json
git commit -m "chore(deps): bump some-package to 2.1.0"
```

---

### Multi-file Bugfix and Hardening

**Trigger:** When you want to fix bugs or improve reliability across a subsystem.  
**Command:** `/fix-bug`

1. Edit implementation files (e.g., `scripts/`, `hooks/`, `ecc2/src/`).
2. Update related config/metadata files (e.g., `hooks.json`).
3. Update/add tests in `tests/`.
4. Commit with `fix:` referencing the subsystem.

**Example:**
```sh
git add scripts/lib/session-manager.js tests/lib/session-manager.test.js
git commit -m "fix(session): handle missing session edge case"
```

---

### Documentation Update

**Trigger:** When you need to clarify, add, or update documentation.  
**Command:** `/update-docs`

1. Edit documentation files (`README.md`, `AGENTS.md`, `commands/*.md`, etc.).
2. Commit with `docs:` or as part of a feature/fix PR.

**Example:**
```sh
git add README.md
git commit -m "docs: document new install autodetection"
```

---

## Testing Patterns

- Test files use the pattern `*.test.js` and are placed in `tests/` directories (`tests/scripts/`, `tests/lib/`, `tests/hooks/`).
- Testing framework is not explicitly specified; check existing test files for patterns.
- Example test file:
  ```js
  // tests/lib/session-manager.test.js
  const { startSession } = require('../../scripts/lib/session-manager');
  test('should start session', () => {
    expect(startSession()).toBeTruthy();
  });
  ```

---

## Commands

| Command             | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| /new-ecc2-feature   | Start a new ECC2 agent/session/dashboard feature             |
| /new-install-feature| Add or enhance install/config logic                          |
| /new-hook           | Add or update a hook                                         |
| /update-ci          | Update CI workflow files                                     |
| /bump-dependency    | Bump a dependency version                                    |
| /fix-bug            | Fix a bug or harden logic across multiple files              |
| /update-docs        | Update or clarify documentation                              |
```
