# Installation

## Via skills (recommended)

```bash
npx skills add ibongobe/Antislop-design-system
```

Works with Claude Code, Cursor, Codex, Cline, and other agents that support Agent Skills.

## Manually

Copy the `skills/anti-slop-ds` folder into:

- Claude Code: `.claude/skills/`
- Cursor: `.cursor/skills/`
- Or into the agent's global skills folder

## After installation

Tell the agent:

> Start Antislop Design System. Run onboarding and create the design system in the project.

The agent will read `SKILL.md`, run onboarding, and create a `design-system/` folder with split YAML files.
