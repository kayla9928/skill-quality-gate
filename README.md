# Skill Quality Gate

`skill-quality-gate` is a Codex Skill for independently reviewing a completed
or substantially updated Skill before it is considered ready. It focuses on
trigger and routing boundaries, workflow scope, progressive disclosure,
validation evidence, safety, and representative regression coverage.

It does not create, scaffold, install, or routinely implement Skills. Use an
appropriate implementation workflow first, then apply this quality gate to the
completed result. The gate should not be the sole reviewer of changes to
itself.

## When to use it

Use this Skill when:

- a reusable Skill has just been created;
- a Skill has received a substantial semantic update; or
- you explicitly want to audit an existing Skill.

Do not use it for ordinary ideation, routine implementation, installation,
non-semantic edits, or structural validation alone.

## Contents

- `SKILL.md` — activation boundaries, review workflow, validation boundary,
  and report contract.
- `agents/openai.yaml` — Codex display metadata and default invocation prompt.
- `references/quality-checklist.md` — semantic review checklist and applicable
  risk overlays.
- `references/evaluation-templates.md` — templates for missing or changed
  evaluation coverage.
- `references/gotchas.md` — known review failure mechanisms.
- `evaluation/trigger-cases.md` — activation and exclusion specifications.
- `evaluation/quality-cases.md` — representative review-quality
  specifications.

The files under `evaluation/` are specifications. Their presence is not
evidence that the cases were executed.

## Installation

Clone this repository into your personal Agent Skills directory:

```shell
git clone https://github.com/kayla9928/skill-quality-gate.git "$HOME/.agents/skills/skill-quality-gate"
```

Codex normally detects Skill changes automatically. If the Skill does not
appear, restart Codex.

## Usage

Invoke the Skill explicitly in Codex:

```text
$skill-quality-gate review this completed Skill for behavioral regressions,
routing errors, and validation gaps.
```

Codex may also select it implicitly when a request matches the description in
`SKILL.md`.

## Review output

Depending on the review, the report may contain:

- a `Pass`, `Needs Work`, or `High Risk` verdict;
- completion-blocking findings and required fixes;
- validation evidence and explicit gaps;
- trigger and evaluation coverage; and
- material residual risk.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
