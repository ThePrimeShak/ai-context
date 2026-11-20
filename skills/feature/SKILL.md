---
name: feature
description: Plan web app features from the project overview, load a spec, implement it on a work branch, test, review, explain, or complete a local dev merge.
---

# Feature workflow

Read `AGENTS.md`, `context/coding-standards.md`, and `context/current-feature.md` from the repository root. Read the active or requested spec where applicable. Follow the action requested by the owner.

| Action | Purpose |
| --- | --- |
| [plan](actions/plan.md) | Turn the agreed project scope into feature specs |
| [load](actions/load.md) | Select one spec and record it as active |
| [start](actions/start.md) | Create or resume the work branch and implement the spec |
| [test](actions/test.md) | Check the specified behavior |
| [review](actions/review.md) | Review the changes against the spec and project requirements |
| [explain](actions/explain.md) | Explain the changes and decisions |
| [complete](actions/complete.md) | Record completion and merge the work branch into local dev |

If the action is omitted, report the active spec and available actions. `load`, `start`, and `complete` are separate requests. Interpret file paths from the repository root unless a link is relative to its document.

## Active record

Keep the headings stable in `context/current-feature.md`.

| State | Status | Spec | Branch |
| --- | --- | --- | --- |
| Idle | Not Started | Empty | Empty |
| Loaded | Not Started | Link to the spec | Empty |
| Implementing | In Progress | Link to the spec | Work branch |

Completion returns the record to idle and appends one entry to `History`.
