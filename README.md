# Virtual Company Workflow

A lightweight, platform-neutral skill for running projects like a small product team.

The main agent acts as project lead and coordinates virtual roles:

- User representative
- Product manager
- Designer
- Architect
- Developer
- QA
- Reviewer

It works in two modes:

- **Single-agent mode**: one agent simulates roles in sequence.
- **Subagent mode**: tools that support subagents can delegate independent roles or tasks.

## Install

The skill lives here:

```text
skills/virtual-company-workflow/
```

### Codex

Copy the skill folder into your Codex skills directory:

```text
%USERPROFILE%\.codex\skills\virtual-company-workflow
```

Then invoke it with:

```text
Use $virtual-company-workflow to run this project like a small product team.
```

### Claude Code

Copy the skill folder into either:

```text
~/.claude/skills/virtual-company-workflow
```

or a project-local skill folder:

```text
.claude/skills/virtual-company-workflow
```

Then ask Claude Code to use the skill:

```text
Use the virtual-company-workflow skill for this project.
```

### Generic Agents

If your tool does not have a skill system, paste the contents of:

```text
skills/virtual-company-workflow/SKILL.md
```

into the system or project instructions, and load files from `references/` only when needed.

## Example

```text
Use $virtual-company-workflow to help me build a simple habit tracker.
Start with user representative and product manager, then summarize the MVP for my approval.
After I approve, create the technical plan and implement it.
```

## Design Goal

This is intentionally small. It is not a full company simulator. It is a practical coordination workflow that helps agents make better product and engineering decisions without endless role-play.
