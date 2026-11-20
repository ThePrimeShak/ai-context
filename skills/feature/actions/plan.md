# Plan features from the overview

1. Use the owner's requested scope and read `context/project-overview.md`. Read existing specs and the active record to avoid duplicating or replacing work. For planning before implementation, use local `dev` as the base and preserve any existing edits.
2. Turn the agreed outcomes into independently verifiable pieces of work. Respect milestones, dependencies, and product non-goals. Surface decisions that block a spec and continue with pieces whose behavior is clear.
3. Write actual specs in `context/features/` with short kebab-case IDs. Use a milestone prefix when it helps show order. Give each spec an outcome, scope, dependencies, acceptance criteria, and verification cases. Refer to relevant domain rule IDs, flows, and screenshot filenames. For an explicitly requested fix spec, use `context/fixes/` and include reproduction steps and the expected result.
4. Link the resulting specs from the relevant roadmap entry when the plan maps to a milestone. Report the files, recommended order, and open decisions. Planning changes documentation only and leaves the active feature record alone.
