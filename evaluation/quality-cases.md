# Quality Evaluation Cases

Use these cases to test review behavior after activation.

## Case 1: Over-broad Description

Input: A Skill whose description activates for reviewing, improving, planning,
writing, or using almost any project artifact.

Required behavior:

- Identify over-triggering and adjacent workflows it collides with.
- Propose a narrower trigger contract.
- Add the smallest relevant positive, negative, and boundary cases.

Forbidden behavior:

- Treat a long keyword list as sufficient trigger accuracy.
- Rewrite unrelated domain instructions without evidence.

## Case 2: Tiny Skill With One Real Risk

Input: A narrow Skill with one deterministic action, a precise description,
and one realistic regression risk.

Required behavior:

- Select focused depth.
- Cover only the demonstrated risk.
- Skip irrelevant overlays and empty report sections.

Forbidden behavior:

- Require a fixed number of examples or cases.
- Expand the Skill merely to satisfy a checklist.

## Case 3: No Behavioral Delta

Input: A proposed paragraph says to be careful, reason thoroughly, and follow
best practices, but names no changed behavior or failure mode.

Required behavior:

- Ask what routing, tool use, authority, validation, or output behavior changes.
- Recommend deletion when no behavioral consequence is identifiable.

Forbidden behavior:

- Keep the paragraph because it sounds generally useful.

## Case 4: Evaluation Presence Without Execution

Input: A Skill contains comprehensive evaluation Markdown files, but no
representative case was executed.

Required behavior:

- Treat the files as specifications.
- Report behavioral validation as unexecuted.
- Run the smallest feasible checks or state the gap.

Forbidden behavior:

- Claim behavioral validation passed because files exist.

## Case 5: Trigger Change With Stale Evaluations

Input: The description and routing boundary changed while evaluations still
encode the previous activation behavior.

Required behavior:

- Identify the mismatch.
- Update only the affected positive, negative, and boundary expectations.
- Require representative evidence before a Pass verdict.

Forbidden behavior:

- Treat stale cases as current proof.

## Case 6: Reusable Gotcha Versus Incident Narrative

Input: A real recurring failure exposes a reusable exception, while a separate
one-off typo caused an unrelated failure.

Required behavior:

- Add the reusable condition, symptom, mechanism, correction, and evaluation
  pointer to `gotchas.md`.
- Exclude the one-off typo and session narrative.
- Avoid lengthening the main workflow.

Forbidden behavior:

- Append both incidents as general rules.
- Duplicate an existing gotcha under a new title.

## Case 7: Self-review Boundary

Input: `skill-quality-gate` itself was substantially changed.

Required behavior:

- Do not use the Skill as sole certification.
- Review against current external guidance, intended contract, structural
  validation, and independent representative cases.
- State any remaining independence limitation.

Forbidden behavior:

- Apply its own checklist and declare itself Pass without external criteria.

## Case 8: Validator Unavailable

Input: Preferred structural validation cannot start because a local dependency
or permission is missing.

Required behavior:

- Preserve the exact failure evidence.
- Run safe fallback checks when useful.
- Report the preferred validation as incomplete.

Forbidden behavior:

- Mark the Skill invalid solely because the validator could not start.
- Claim an unproven fallback is equivalent.

## Case 9: Persistent-state Ownership Conflict

Input: Two Skills claim write authority over the same registry.

Required behavior:

- Select extended depth.
- Identify dual ownership as a material defect.
- Recommend one owner and a narrow bridge contract.
- Apply only relevant persistent-state and filesystem overlays.

Forbidden behavior:

- Duplicate synchronization instructions in both Skills.

## Case 10: Targeted Fix Versus Rewrite

Input: A generally sound Skill has one ambiguous trigger clause and one broken
reference.

Required behavior:

- Preserve valid behavior.
- Recommend the smallest sufficient edits and relevant validation.

Forbidden behavior:

- Rewrite the whole Skill or alter unrelated conventions.

## Case 11: Constraint Necessity

Input: Generic competence advice and a behavior-changing constraint with no stated regression or authority.

Required behavior:

- Remove the generic advice and ask for justification or delete the unjustified constraint.

## Case 12: Placement And Consistency

Input: A project-specific rule in a global Skill, a prose rule enforceable by CI, a paraphrase duplicate, and a general rule with an exception.

Required behavior:

- Classify misplaced, mechanically enforceable, redundant, and legitimate scoped-override findings.
- Check exception precedence and update only affected evaluations.

## Case 13: Vendor-Managed Skill Mistaken For A Personal Skill

Input: A setup command installs an MCP entry, a marked global rule, and a Skill
under a user-visible Skill directory. The user wants to improve the Skill, but
rerunning setup may rewrite the generated files.

Required behavior:

- Classify provenance, canonical source, update mechanism, and write authority
  before recommending changes.
- Treat the target as audit-only while ownership or overwrite behavior remains
  unresolved.
- Prefer a user-owned routing override, configuration surface, wrapper,
  upstream fix, or explicit replacement decision over an in-place vendor-file
  edit.
- Limit validation to the generated surface and its direct user-owned override
  unless a concrete conflict signal justifies expansion.

Forbidden behavior:

- Infer personal ownership solely from a path under the user's Skill directory.
- Modify or retire the generated Skill before checking reinstall and update
  behavior.
- Duplicate the vendor workflow into a same-named personal Skill without an
  explicit replacement and maintenance decision.
