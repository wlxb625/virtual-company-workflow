---
name: virtual-company-workflow
description: Use when the user wants to run a project like a small company or product team, with roles such as user representative, product manager, designer, architect, developer, QA, and reviewer collaborating through a controlled workflow. Works with single-agent simulation and with platforms that support subagents.
---

# Virtual Company Workflow

Use this skill to coordinate project work through a small virtual team. The main agent acts as project lead: it gathers role input, resolves conflicts, asks the real user for decisions, and keeps the work moving.

This skill is platform-neutral. If the host supports subagents, delegate independent roles or implementation tasks. If not, simulate the roles one at a time in the main conversation.

## Core Rules

- Do not let roles free-chat indefinitely. Each role speaks only when its phase needs that perspective.
- Keep the real user as final decision maker for scope, product direction, and trade-offs.
- Prefer a lightweight process for small tasks. Do not create enterprise ceremony unless the project needs it.
- Separate discovery from implementation: align on the product intent before changing code.
- During implementation, assign non-overlapping file or module ownership when using multiple agents.
- The project lead must summarize disagreements and recommend a decision instead of merely forwarding opinions.

## Default Team

- **User representative**: explains user goals, pain points, objections, and failure cases.
- **Product manager**: defines MVP scope, non-goals, priorities, and acceptance criteria.
- **Designer**: clarifies user flow, information architecture, interaction states, and UX risks.
- **Architect**: proposes technical boundaries, data flow, interfaces, risks, and task decomposition.
- **Developer**: implements assigned tasks within clear ownership boundaries.
- **QA**: validates behavior against acceptance criteria and edge cases.
- **Reviewer**: checks maintainability, correctness, security, and unnecessary complexity.
- **Project lead**: coordinates the process, chooses the next step, integrates outputs, and reports to the real user.

Read `references/roles.md` when role responsibilities need more detail.

## Workflow

1. **Intake**
   - Restate the user's goal in one short paragraph.
   - Identify whether the request is discovery-only, planning, implementation, or review.
   - Choose the lightest workflow that can succeed.

2. **Product alignment**
   - Ask the user representative for likely user needs and objections.
   - Ask the product manager to define MVP scope, non-goals, and acceptance criteria.
   - Summarize conflicts and ask the real user to approve or adjust scope.

3. **Design and technical shape**
   - Ask the designer for the user flow and important states.
   - Ask the architect for module boundaries, data flow, implementation risks, and parallelizable tasks.
   - Present a concise plan and get user approval before implementation when scope is non-trivial.

4. **Execution**
   - Assign tasks to developers with explicit ownership, inputs, outputs, and constraints.
   - If using subagents, tell each developer they are not alone in the codebase and must not revert others' work.
   - The project lead integrates results and resolves conflicts.

5. **Validation**
   - QA checks acceptance criteria and edge cases.
   - Reviewer checks code quality and risk.
   - The project lead runs or requests appropriate verification and reports the outcome.

See `references/workflow.md` for phase checklists and `references/prompt-templates.md` for reusable prompts.

## Scaling Guidance

For a small skill, script, or single-file change, use a compact version:

1. User representative: "Would someone actually use this?"
2. Product manager: "What is the smallest useful version?"
3. Architect/developer: "What is the simplest reliable implementation?"
4. QA/reviewer: "How do we know it works and did not become too complex?"

For larger projects, produce these artifacts:

- Product brief or PRD
- Technical plan
- Task ownership map
- Acceptance checklist
- Final verification report

## Output Style

When presenting role input, use short labeled sections. Example:

```text
User representative: ...
Product manager: ...
Project lead recommendation: ...
Decision needed: ...
```

Avoid long fictional dialogue. The goal is better decisions, not role-play theater.
