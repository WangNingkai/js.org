```markdown
# js.org Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development and contribution patterns for the [js.org](https://github.com/js-org/js.org) repository. The project is a community-driven initiative to provide free `.js.org` subdomains for JavaScript projects. The codebase is primarily JavaScript, with no major framework dependencies, and relies on clear conventions for file naming, imports/exports, and collaborative workflows via GitHub.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for all file names.  
  _Example:_  
  ```
  cnames_active.js
  pull_request_template.md
  ```

- **Import Style:**  
  Use relative imports for modules.  
  _Example:_  
  ```js
  import { validateSubdomain } from './utils/validate_subdomain.js';
  ```

- **Export Style:**  
  Use named exports.  
  _Example:_  
  ```js
  // In utils/validate_subdomain.js
  export function validateSubdomain(name) { ... }
  ```

- **Commit Messages:**  
  Freeform, typically concise (average ~39 characters), no strict prefixing.

## Workflows

### Add New JS.org Subdomain
**Trigger:** When someone wants to register a new js.org subdomain for their project  
**Command:** `/add-subdomain`

1. Edit `cnames_active.js` to add a new entry for the requested subdomain.
   ```js
   // Example addition in cnames_active.js
   "myproject": "myproject.github.io",
   ```
2. Open a pull request with the change.
3. Wait for review and merge after approval.

---

### Update GitHub Actions Workflows
**Trigger:** When improving, splitting, or fixing CI/CD workflows (e.g., validation, PR comments)  
**Command:** `/update-workflow`

1. Edit workflow YAML files in `.github/workflows` (e.g., `comment.yml`, `validate.yml`).
   ```yaml
   # Example: .github/workflows/validate.yml
   name: Validate Subdomains
   on: [pull_request]
   jobs:
     validate:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v2
         - run: node scripts/validate.js
   ```
2. Optionally update `PULL_REQUEST_TEMPLATE.md` if related to PR validation.
3. Open a pull request with the changes.
4. Merge after review.

---

### Merge Main into Feature Branch
**Trigger:** When a contributor needs to bring their branch up to date with the latest master changes before merging  
**Command:** `/sync-with-main`

1. Merge `master` into your feature or patch branch.
   ```sh
   git checkout my-feature-branch
   git fetch origin
   git merge origin/master
   # Resolve any conflicts if prompted
   git push
   ```
2. Resolve any conflicts if necessary.
3. Push the updated branch.

## Testing Patterns

- **Framework:** Not explicitly detected.
- **Test Files:** Use the pattern `*.test.*`.
  _Example:_  
  ```
  utils/validate_subdomain.test.js
  ```
- **Typical Test Structure:**  
  ```js
  // utils/validate_subdomain.test.js
  import { validateSubdomain } from './validate_subdomain.js';

  test('validates a correct subdomain', () => {
    expect(validateSubdomain('myproject')).toBe(true);
  });
  ```

## Commands

| Command           | Purpose                                                      |
|-------------------|--------------------------------------------------------------|
| /add-subdomain    | Register a new js.org subdomain (edit `cnames_active.js`)    |
| /update-workflow  | Update or split GitHub Actions workflow files                |
| /sync-with-main   | Merge latest master into your feature or patch branch        |
```
