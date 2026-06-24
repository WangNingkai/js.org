---
name: add-new-js-org-subdomain
description: Workflow command scaffold for add-new-js-org-subdomain in js.org.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-js-org-subdomain

Use this workflow when working on **add-new-js-org-subdomain** in `js.org`.

## Goal

Adds a new subdomain to js.org by updating the cnames_active.js file.

## Common Files

- `cnames_active.js`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit cnames_active.js to add a new entry for the requested subdomain.
- Open a pull request with the change.
- Merge the pull request after review.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.