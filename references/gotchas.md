# Reusable Gotchas

Add a gotcha only after a real failure or recurring review error exposes a
reusable exception.

Record only:

- condition;
- observable symptom;
- why the normal path fails;
- smallest safe correction;
- relevant evaluation case.

Do not store session narratives, one-off mistakes, duplicated guidance, or
general advice. Merge overlapping gotchas instead of appending variants.

## Known Gotchas

### Evaluation Files Are Not Execution Evidence

- **Condition:** An audit finds well-written evaluation cases but no evidence
  that representative cases ran.
- **Symptom:** The review claims behavioral validation passed because files
  exist.
- **Why it fails:** Evaluation documents define expected behavior; they do not
  prove current behavior.
- **Correction:** Report the cases as unexecuted and run the smallest relevant
  checks when feasible.
- **Evaluation:** `quality-cases.md` — Evaluation Presence Without Execution.

### Validator Startup Failure Is Not A Skill Verdict

- **Condition:** A structural validator cannot start because of a missing
  dependency, permission, or environment mismatch.
- **Symptom:** The Skill is marked invalid, or validation is reported as
  passed using an unproven substitute.
- **Why it fails:** The result describes the validator environment, not the
  Skill's structure.
- **Correction:** Preserve the exact failure, run safe fallback checks when
  useful, and report the remaining gap.
- **Evaluation:** `quality-cases.md` — Validator Unavailable.

### Self-review Cannot Be The Sole Quality Gate

- **Condition:** `skill-quality-gate` itself is the review target.
- **Symptom:** The Skill applies its own criteria and declares itself complete.
- **Why it fails:** The reviewer and reviewed contract share the same blind
  spots.
- **Correction:** Use current external guidance and independent representative
  cases; do not treat this Skill's output as sole certification.
- **Evaluation:** `quality-cases.md` — Self-review Boundary.

### User-visible Skill Paths May Still Be Installer-managed

- **Condition:** A vendor or plugin setup command writes a Skill into a
  user-visible Skill directory together with configuration or marked global
  instructions.
- **Symptom:** A review treats the Skill as user-owned and recommends a direct
  edit that disappears or conflicts after setup runs again.
- **Why it fails:** File location does not establish canonical ownership; the
  installer may retain update authority and overwrite generated files or
  marked sections.
- **Correction:** Verify provenance, source, update mechanism, and overwrite
  behavior first. Keep the vendor file audit-only by default and place user
  policy on a separate durable surface unless an explicit fork or replacement
  is approved.
- **Evaluation:** `quality-cases.md` — Vendor-Managed Skill Mistaken For A
  Personal Skill.
