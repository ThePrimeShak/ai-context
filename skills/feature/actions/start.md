# Start implementation

1. Read the loaded spec and relevant overview sections. Resolve blockers that affect the next change. If the recorded work branch is already checked out, inspect the current changes and resume the agreed work.
2. For new work, verify the checkout is on `dev` with the unstaged active record as its only pending change. Create and switch to `feature/<id>` or `fix/<id>`. If the branch exists, inspect it before deciding whether it belongs to this spec. Preserve its commits and pending edits.
3. Record the branch in `context/current-feature.md` and set the status to `In Progress`. Read the existing code and tests. For a UI change, look at the relevant files in `context/screenshots/` when available and apply their visual direction within the product's conventions. For a fix, reproduce or trace the issue and record the cause.
4. Show the ordered goal checklist before the first implementation edit. If resuming, read `Goals`, `Notes`, and the existing diff to identify the current goal and any pending owner decision. Implement one goal at a time using the edit approval process in `AGENTS.md`. For domain logic, show the tests before the implementation.
5. Run the checks relevant to the current goal and record the result. Check off the goal only when the evidence supports it. Summarize the change and why it was made, then wait for the owner to review it before starting the next goal.
6. After the last goal is reviewed, report the verification results and remaining checks. Wait for the owner's `complete` request before merging.
