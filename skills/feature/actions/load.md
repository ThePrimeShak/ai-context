# Load a spec

1. Read the active record. If the requested spec is already active, report its state and stop. If another is active, ask how to handle it before replacing the record.
2. Check the branch, working tree, and pending Git operations. With a clean checkout, switch to existing local `dev` when needed. If `dev` is missing, ask which commit or branch should be its starting point.
3. Resolve the requested ID in `context/features/` or `context/fixes/` on `dev`, or use the explicit spec path in one of those directories. Ask which path to use when an ID is ambiguous. If the spec exists only in uncommitted changes, report that it needs to be recorded on `dev` first. If it is missing, suggest `feature plan` or ask for its path.
4. Read the spec and the relevant parts of the overview. Update only `context/current-feature.md`. Add the title in the main heading, set the relative link under `Spec`, copy the acceptance criteria into `Goals` as unchecked checklist items, and record scope, dependencies, references, and verification details under `Notes`. Preserve `History`, keep `Branch` empty, and set `Status` to `Not Started`.
5. Leave the active record unstaged. Summarize the goals, blockers, and decisions still open. Wait for `start`.
