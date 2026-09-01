---
name: skill-quality-gate
description: Use after creating a reusable Codex Skill, after a substantial semantic update, or when explicitly auditing an existing Skill. Review trigger and routing boundaries, workflow scope, progressive disclosure, validation evidence, safety, and representative regression coverage. Do not use for ideation, routine implementation, installation, non-semantic edits, or structural validation alone.
---

# Skill Quality Gate

Perform an independent semantic and regression review after implementation is
complete, or audit an existing Skill when explicitly requested.

Do not create, scaffold, install, or routinely implement a Skill with this
gate. Run structural validation separately. Do not use this Skill as the sole
reviewer of changes to itself; review those changes independently against
current external guidance and representative cases.

## Review Flow

1. Establish target provenance, update ownership, and write authority before
   recommending in-place changes. Distinguish personal or project-local Skills
   from system-managed, plugin-managed, installer-generated, or other
   externally managed Skills. Default externally managed targets to audit-only;
   prefer a user-owned override, configuration surface, wrapper, upstream fix,
   or explicit replacement decision unless the user has authorized a durable
   local fork with understood update consequences.
2. Establish the requested scope and inspect the change set when available. If
   the change set is unavailable, identify the behavior being reviewed before
   expanding scope.
3. Start with changed files and directly relevant resources. Read additional
   references, scripts, assets, and evaluations only when they can affect the
   changed behavior or a plausible failure mode.
4. Choose the lightest review depth that can catch the material risks:

   | Depth | Use When | Emphasis |
   |---|---|---|
   | `focused` | Frontmatter, one narrow behavior, or a small isolated edit | Changed contract and relevant validation |
   | `standard` | Workflow, references, templates, outputs, or repeated behavior changed | Semantic checklist, progressive disclosure, activation and output coverage |
   | `extended` | Persistent-state authority, broad routing, external or irreversible actions, or unresolved cross-file consistency are material | Standard review plus only applicable authority, safety, and freshness overlays |

5. Run the strongest applicable non-destructive structural and behavioral
   checks available. Treat evaluation files as specifications, not evidence
   that their cases were executed.
6. Report only findings that change completion status, required edits,
   validation confidence, or material residual risk.

For each material retained constraint, apply the necessity, placement, and
consistency checks in [quality-checklist.md](references/quality-checklist.md).
Start with the changed contract and direct consumers; do not inventory unrelated
resources without a concrete conflict signal.

## References

- Read [quality-checklist.md](references/quality-checklist.md) for the semantic
  checklist and applicable risk overlays.
- Read [evaluation-templates.md](references/evaluation-templates.md) only when
  evaluation coverage is missing, stale, or changed.
- Search or read [gotchas.md](references/gotchas.md) only when the audit matches
  a known failure signal or a newly observed failure may justify a reusable
  entry.

## Validation Boundary

Run the strongest applicable structural validation separately. If the
preferred validator is unavailable, use a safe local fallback when available
and report the gap. Do not infer structural validity or invalidity from
validator availability alone.

Retain an instruction, example, template field, or reference only when it has
a justified durable behavioral effect and belongs on this Skill's surface.
Remove generic advice, repeated host behavior, and project-specific rules with
no such justification. Do not add a rule-extraction script unless representative
tests show a repeated miss it can catch with acceptable false positives.

## Report

Include only the applicable sections:

- **Verdict:** `Pass`, `Needs Work`, or `High Risk`, with the decisive reason.
- **Required Findings And Fixes:** Completion-blocking or behavior-changing
  issues only.
- **Validation Evidence:** Checks executed, results observed, and explicit
  gaps.
- **Trigger And Evaluation Coverage:** Include when activation or output
  behavior is in scope.
- **Residual Risk:** Include only when material.

Use `High Risk` only for material safety, authority, integrity, or irreversible
consequences. Use `Needs Work` for meaningful but containable defects. Use
`Pass` only when no blocking finding remains and relevant validation supports
the reviewed scope.

Preserve valid domain behavior and recommend the smallest verifiable edits.
