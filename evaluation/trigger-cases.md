# Trigger Evaluation Cases

Evaluate activation separately from the quality of the eventual review.

| Type | Prompt | Expected Activation | Expected Route | Reason |
|---|---|---|---|---|
| Direct | "This reusable Skill is complete. Run the final semantic quality gate." | Trigger | Standard review | A completed new Skill needs semantic and regression review. |
| Direct | "Audit why this existing Skill keeps over-triggering." | Trigger | Trigger audit | Explicit audit of an existing Skill. |
| Direct | "I substantially changed the workflow and approval boundary; run regression review." | Trigger | Standard or extended review | Behavior and authority changed. |
| Direct | "I changed this Skill's description and routing boundary." | Trigger | Focused or standard review | Activation behavior changed even if the body did not. |
| Indirect | "Structural validation passed; now check activation boundaries and representative behavior." | Trigger | Semantic review | The request describes this gate without naming it. |
| Incomplete | "Check whether this Skill is reliable." | Trigger | Discover the target and state missing context | Explicit audit, even when scope is incomplete. |
| Negative | "Create a research-management Skill from scratch." | Do not trigger yet | Use `skill-creator`; gate after completion | Initial design and implementation are outside this gate. |
| Negative | "Install this Skill from a GitHub repository." | Do not trigger | Use the installer workflow | Installation is outside scope. |
| Negative | "Use medical-review-editor to revise this manuscript." | Do not trigger | Use the named domain Skill | Ordinary Skill use is not a Skill audit. |
| Negative | "Diagnose a null-pointer bug in this application." | Do not trigger | Normal code diagnosis | The target is application code, not a Codex Skill. |
| Negative | "Fix this broken link in SKILL.md." | Do not trigger by default | Make the narrow edit and run link validation | A non-semantic edit does not need semantic review. |
| Negative | "Correct spelling and UI wording in openai.yaml." | Do not trigger by default | Run applicable structural checks | User-visible meaning and routing are unchanged. |
| Negative | "Explain what Codex Skills are." | Do not trigger | Answer from official documentation | General explanation is not an audit. |
| Boundary | "I fixed one typo; please explicitly run a final review." | Trigger | Focused review | Explicit audit authorization applies, but depth stays narrow. |
| Boundary | "Create a Skill and run the quality gate when implementation is complete." | Trigger only after completion | `skill-creator` first, then this gate | The gate must not take over implementation. |
| Boundary | "The validator cannot start because YAML is missing; audit what is actually known." | Trigger | Focused validation audit | Validator availability is not a Skill verdict. |
| Boundary | "Audit only; do not modify files." | Trigger | Audit-only | Review authorization does not imply writes. |
| Boundary | "Optimize this Skill." | Trigger only after implementation | Use `skill-creator` for the authorized update, then run this gate after implementation | The gate must not become the Skill updater or iteration optimizer. |
| Boundary | "Audit skill-quality-gate itself." | Do not use it as sole reviewer | Independent review against external guidance and representative cases | Self-review cannot be sole certification. |
| Boundary | "Only the evaluation contract changed." | Trigger | Focused or standard regression review | Evaluation semantics affect completion evidence. |
| Boundary | "This new Skill rule changes behavior, but why must it persist?" | Trigger | Focused necessity and placement review | Behavioral delta alone is insufficient. |
| Boundary | "A Skill and AGENTS.md both state this rule." | Trigger | Focused consistency review | A concrete ownership conflict exists. |
| Boundary | "Audit this Skill that a vendor setup command installed. Should I edit it directly?" | Trigger | Focused provenance and update-ownership audit; default to audit-only | Installation location does not establish write ownership or update durability. |
