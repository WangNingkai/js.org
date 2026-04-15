---
name: update-github-actions-workflows
description: Workflow command scaffold for update-github-actions-workflows in js.org.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-github-actions-workflows

Use this workflow when working on **update-github-actions-workflows** in `js.org`.

## Goal

Updates or splits GitHub Actions workflow files for CI/CD or automation improvements.

## Common Files

- `.github/workflows/comment.yml`
- `.github/workflows/validate.yml`
- `PULL_REQUEST_TEMPLATE.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit one or more workflow YAML files in .github/workflows (e.g., comment.yml, validate.yml).
- Optionally update PULL_REQUEST_TEMPLATE.md if related to PR validation.
- Open a pull request with the changes.
- Merge the pull request after review.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.