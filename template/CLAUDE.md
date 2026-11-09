# Pilot project repository

This is a pilot project repository of KISENO. Besides its own goal, the project feeds one or more AI service blueprints: `casebook.yaml` names them, with the case slug and the research question IDs per blueprint. Read it at the start of every session; if it still holds `changeme`, run the kick-off first (`.claude/guides/kickoff.md`).

Insights for a blueprint (a design decision, an abandoned approach, an evaluation result, an interview) go into the engineer's local clone of `blueprint-<slug>/casebook/` through the `casebook-entry` skill, never by hand and never without the engineer's confirmation. Nothing leaves this repository without the `redact` script; partner persons, contact data and partner document text never reach a casebook. Before every `/compact` the `PreCompact` hook in `.claude/settings.json` scans the session for casebook entries (stub until `casebook-scan` exists).

Skills from the kisz marketplace: `casebook-entry` and `casebook-scan` (plugin kisz-code, planned), `kisz-context` for the project page, `kisz-writing` for prose, `sbatch` and the `cluster-run` agent for the HPI cluster. Project setup, tests, lint and formatting are described in `development.md`.
