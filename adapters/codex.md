# Codex Adapter

Install:

```text
%USERPROFILE%\.codex\skills\virtual-company-workflow
```

Recommended prompt:

```text
Use $virtual-company-workflow to run this project like a small product team.
You are the project lead. Use subagents only for independent tasks with clear ownership.
```

Codex-specific guidance:

- Use the main thread as project lead.
- Use explorer agents for focused codebase questions.
- Use worker agents for implementation tasks with disjoint ownership.
- Tell workers they are not alone in the codebase and must not revert others' work.
- Keep final integration, verification, and user-facing decisions in the main thread.
