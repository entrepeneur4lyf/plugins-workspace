```markdown
# plugins-workspace Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `plugins-workspace` TypeScript codebase. You'll learn about file organization, import/export styles, commit message conventions, and how to write and run tests. This guide is ideal for contributors seeking to maintain consistency and quality in the project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `pluginManager.ts`, `userSettings.ts`

### Import Style
- Use **relative imports** for modules within the repository.
  - Example:
    ```typescript
    import { getConfig } from './configManager';
    ```

### Export Style
- Use **named exports** instead of default exports.
  - Example:
    ```typescript
    // In pluginManager.ts
    export function loadPlugins() { /* ... */ }
    export const PLUGIN_VERSION = '1.0.0';
    ```

### Commit Messages
- Follow the **Conventional Commits** specification.
- Use the `chore` prefix for maintenance and non-feature changes.
  - Example:  
    ```
    chore: update dependencies and fix lint errors
    ```

## Workflows

### Commit Changes
**Trigger:** When making any code or configuration changes  
**Command:** `/commit-changes`

1. Make your code changes following the coding conventions.
2. Stage your changes:
    ```
    git add .
    ```
3. Commit using a conventional commit message:
    ```
    git commit -m "chore: describe your change here"
    ```
4. Push your changes:
    ```
    git push
    ```

### Add a New Module
**Trigger:** When adding a new feature or utility  
**Command:** `/add-module`

1. Create a new file using camelCase naming, e.g., `featureToggle.ts`.
2. Implement your logic using named exports.
    ```typescript
    export function toggleFeature(flag: string) { /* ... */ }
    ```
3. Import the module using a relative path where needed.
    ```typescript
    import { toggleFeature } from './featureToggle';
    ```
4. Write corresponding tests (see Testing Patterns).

### Run Tests
**Trigger:** To verify code correctness before committing or merging  
**Command:** `/run-tests`

1. Identify test files (pattern: `*.test.*`).
2. Use the project's test runner (framework unknown; check project scripts or documentation).
3. Run all tests:
    ```
    npm test
    ```
    or, if using another runner:
    ```
    yarn test
    ```

## Testing Patterns

- Test files follow the `*.test.*` naming pattern, e.g., `pluginManager.test.ts`.
- The testing framework is not specified; check for scripts in `package.json` or ask a maintainer.
- Example test file structure:
    ```typescript
    import { loadPlugins } from './pluginManager';

    describe('loadPlugins', () => {
      it('should load all plugins', () => {
        // test implementation
      });
    });
    ```

## Commands
| Command         | Purpose                                         |
|-----------------|-------------------------------------------------|
| /commit-changes | Guide for committing changes with conventions   |
| /add-module     | Steps to add a new module following standards   |
| /run-tests      | Instructions for running the test suite         |
```
