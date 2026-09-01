# Evaluation Templates

Use these templates when a skill needs lightweight quality coverage. Keep cases short and directly tied to likely failures.

## Trigger Cases Template

```md
# Trigger Evaluation Cases

## Positive Cases

| Prompt | Expected | Reason |
|---|---|---|
|  | Trigger |  |

## Negative Cases

| Prompt | Expected | Reason |
|---|---|---|
|  | Do not trigger |  |

## Boundary Cases

| Prompt | Expected | Reason |
|---|---|---|
|  |  |  |
```

## Quality Cases Template

```md
# Quality Evaluation Cases

## Case 1: Typical Use

Prompt:

Expected checks:

-

## Case 2: Boundary Or Error Case

Prompt:

Expected checks:

-

## Case 3: Negative Or Out-Of-Scope Case

Prompt:

Expected checks:

-
```

## Representative Coverage

- Select the smallest set of cases that represents likely activation successes, over-trigger failures, ambiguous boundaries, and important output regressions.
- Include positive and negative cases when the trigger contract could be confused with adjacent skills or ordinary work.
- Include boundary cases for materially different routes, stop conditions, or authorization limits.
- Add quality cases for examples, safety gates, templates, path consistency, or other behavior only when central to the skill.
- Update cases when a semantic change alters the description, routing, approval or stopping boundary, persistent-state authority, or output contract.
- Do not update cases for non-semantic edits unless observable behavior changes.
- Treat these files as specifications; record execution evidence separately.
- Add or remove cases in response to observed failures; do not satisfy a fixed quota.
