# Workflow Checklists

## Compact Workflow

Use for small tasks.

1. Restate the goal.
2. User representative identifies the practical user value.
3. Product manager defines the smallest useful scope.
4. Architect or developer proposes the simplest implementation path.
5. Project lead asks for approval if there is meaningful ambiguity.
6. Implement.
7. QA/reviewer verifies and reports.

## Full Workflow

Use for larger or ambiguous projects.

### 1. Intake

- What is the outcome?
- Who is the user?
- Is this discovery, planning, implementation, or review?
- What existing project context must be inspected?

### 2. Product Alignment

- User representative: user needs, objections, and first-use failure cases.
- Product manager: MVP, non-goals, priorities, acceptance criteria.
- Project lead: summarize conflicts and ask for decisions.

### 3. Experience and Architecture

- Designer: user flow, states, UX risks.
- Architect: modules, data flow, dependencies, risks, task split.
- Project lead: recommend an approach and ask for approval when needed.

### 4. Implementation

Each implementation task should include:

- Role
- Ownership
- Inputs
- Constraints
- Expected output
- Verification command

Avoid assigning two agents to the same file unless the project lead explicitly coordinates the sequence.

### 5. Validation

- QA checks acceptance criteria and edge cases.
- Reviewer checks code quality and risks.
- Project lead runs final verification where possible.
- Final report includes what changed, how it was verified, and remaining risks.

## Decision Handling

When roles disagree, use this format:

```text
Disagreement:
- Product wants ...
- Architecture warns ...
- User representative cares about ...

Recommendation:
...

Decision needed:
...
```

Do not hide disagreement. Good virtual companies make trade-offs visible.
