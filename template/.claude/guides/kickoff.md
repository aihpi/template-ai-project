# Kick-off: filling casebook.yaml

Done once at project start, by the engineer together with Claude, before the first entry is written.

1. List the solution classes this project touches. A project usually feeds one or more blueprints; a blueprint that does not exist yet is created from `aihpi/template-blueprint` first.
2. For each blueprint, open its `blueprint/02_01_research_questions.md` and pick the IDs this project will answer. Only those IDs go into `questions`.
3. Fill `partner` with the organization name, `since` with today's date, and leave `until` empty.
4. Check that every named blueprint has a local clone at `$KISZ_BLUEPRINTS_DIR/blueprint-<slug>`, up to date with `main`. `KISZ_BLUEPRINTS_DIR` is the folder that holds your blueprint clones on this machine; it lives in `~/.config/kisz/blueprints.env` as `KISZ_BLUEPRINTS_DIR=<path>`, which the casebook skills read. Check that the file exists; if not, ask the engineer for the folder and create the file. When it is missing, the skills use `~/Repositories`.
5. Commit `casebook.yaml`. When the project later stops feeding a blueprint, set `until`; when the blueprint renames its slug or research questions, its owner opens a pull request here.

Example, the GrundschutzKI pilot project, which yields two cases:

```yaml
schema: 1
project: pilotproject-GrundschutzKI
partner: fghgsd
blueprints:
  - slug: rag
    case: grundschutzki
    questions: [RQ1, RQ2]
    since: 2025-10-01
    until: 2026-05-31
  - slug: evaluation
    case: grundschutzki
    questions: [RQ1]
    since: 2026-01-15
    until: 2026-05-31
```

The research question IDs in the example are placeholders until blueprint-rag and blueprint-evaluation define theirs.
