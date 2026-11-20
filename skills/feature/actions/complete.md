# Complete the feature

1. On the owner's `complete` request, verify that the current branch matches the active work branch in `context/current-feature.md`. The work branch must be separate from `dev` and `main`. Confirm local `dev` exists and check for in-progress Git operations. Review all commits to be merged and staged, unstaged, and untracked changes. Stop if completion would include or interfere with unrelated work.
2. Verify the active spec's acceptance criteria and run the relevant configured checks as described in `context/coding-standards.md`. If a required check fails or cannot run, continue once it passes or the owner explicitly accepts that gap.
3. On the work branch, append one entry with the spec ID and outcome to `History`. Return the heading to `# Current Feature`, set `Status` to `Not Started`, and clear the contents of `Spec`, `Branch`, `Goals`, and `Notes`. Keep all headings. Stage only the reviewed feature changes and this record. Follow the repository's commit conventions and note the work branch tip.
4. With a clean checkout, switch to local `dev`. Confirm it is checked out, then merge the work branch using its local ref, for example `git merge --no-edit refs/heads/feature/export-report`. If the checkout or merge fails, report the failure and preserve the work branch. If there is a merge conflict, report the files and wait for direction before resolving or aborting the merge.
5. Verify that the recorded work tip is an ancestor of local `dev`. Report the result, commit, and checks. Pushes and branch cleanup are separate actions.

## Resume an interrupted completion

Inspect the Git state and the pending or committed completion entry before retrying. Ask for the exact branch if it is ambiguous. If a previous commit failed and its reviewed changes are still staged on the work branch, verify that state before retrying the commit. Keep the existing history entry.

If the completion commit already exists, resume from the merge step after confirming the checkout is clean and no Git operation is active. If `dev` already contains the recorded tip, report success. If a merge is still in progress, report its status and follow the owner's direction.
