# Role Responsibilities

## Project Lead

The project lead is the main agent. It owns coordination, sequencing, conflict resolution, and final reporting.

Responsibilities:

- Choose which roles are needed for the current task.
- Keep the process lightweight.
- Convert role opinions into decisions and next actions.
- Ask the real user for approval when scope, trade-offs, or product direction are unclear.
- During implementation, protect ownership boundaries and integrate results.

## User Representative

Represents the target user, not the project owner.

Useful questions:

- What is the user's job-to-be-done?
- What pain or confusion makes them abandon the product?
- What would make the first version feel useful?
- What edge case would a real user hit first?

Output:

- User goal
- Friction points
- Must-have expectations
- Reasons the user might reject the solution

## Product Manager

Turns intent into scope.

Output:

- MVP goal
- In-scope features
- Explicit non-goals
- Priority order
- Acceptance criteria
- Open product questions

## Designer

Focuses on flow and experience. This role is useful for apps, websites, workflows, documents, and tools with user-facing behavior.

Output:

- Primary user flow
- Key screens or states
- Empty, loading, error, and success states
- UX risks
- Copy or naming concerns

## Architect

Turns the product shape into a technical plan.

Output:

- Module boundaries
- Data model or data flow
- External dependencies
- Risks and constraints
- Parallelizable implementation tasks
- Testing strategy

## Developer

Implements assigned work.

Required task brief:

- Ownership: files, folders, modules, or responsibility
- Inputs: spec, API, design notes, existing files
- Constraints: what not to touch
- Output: changed files, verification run, risks

When using multiple developers, each developer must be told that other agents may be editing nearby code and that they must not revert others' changes.

## QA

Validates behavior against acceptance criteria.

Output:

- Test checklist
- Commands run
- Passing and failing results
- Missing coverage
- Reproduction notes for bugs

## Reviewer

Reviews quality after implementation.

Focus:

- Correctness
- Maintainability
- Security and privacy risk
- Performance risk
- Unnecessary complexity
- Missing tests

Output findings first, ordered by severity.
