# Start implementation

1. Read the loaded spec and relevant overview sections. Resolve blockers that affect the next change. If the recorded work branch is already checked out, inspect the current changes and resume the agreed work.
2. For new work, verify the checkout is on `dev` with the unstaged active record as its only pending change. Create and switch to `feature/<id>` or `fix/<id>`. If the branch exists, inspect it before deciding whether it belongs to this spec. Preserve its commits and pending edits.
3. Record the branch in `context/current-feature.md` and set the status to `In Progress`. Read the existing code and tests. For a UI change, look at the relevant files in `context/screenshots/` when available and apply their visual direction within the product's conventions. For a fix, reproduce or trace the issue and record the cause.
4. Implement the acceptance criteria in order and mark each one verified when there is evidence. Record decisions, checks, and remaining gaps when useful for resuming work. Report the result and wait for the owner's `complete` request before merging.
