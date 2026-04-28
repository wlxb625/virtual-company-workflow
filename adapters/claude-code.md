# Claude Code Adapter

Install globally:

```text
~/.claude/skills/virtual-company-workflow
```

Install for one project:

```text
.claude/skills/virtual-company-workflow
```

Recommended prompt:

```text
Use the virtual-company-workflow skill to run this project like a small product team.
Start with product alignment before implementation.
```

Claude Code-specific guidance:

- Use the main conversation as project lead.
- If subagents are available, delegate bounded research, implementation, or review tasks.
- If subagents are not available, simulate the roles sequentially.
- Keep role outputs concise and decision-oriented.
