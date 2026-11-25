<div align="center">

# Anti-Slop DS

Build your design system and remove AI slop from projects you make with AI agents.

<code>npx skills add ibongobe/Antislop-design-system</code>

[Install](#install) · [Before / After](#before--after) · [How it works](#how-it-works) · [Docs](#docs)

</div>

---

**Anti-Slop DS** gives the agent a single source of truth — your design system in YAML. The agent takes colors, radii, components, states, and text only from there. If something is missing, it stops and asks instead of inventing.

This is not a post-hoc filter. It is a source of truth the agent reads before generating any UI.

## Before / After

Examples will be added after test runs on real projects. Below is the grid structure that will be filled.

### UI

| **Before: without Anti-Slop DS** | **After: Anti-Slop DS** |
|:--|:--|
| <img src="assets/examples/ui-before.png" alt="AI slop: inconsistent colors, random radii, No data" width="100%"> | <img src="assets/examples/ui-after.png" alt="Consistent interface from the design system" width="100%"> |
| Different colors across screens, random radii, "No data", buttons of different sizes. | Everything from YAML: one set of colors, radii, states, and texts. The agent does not invent. |

### Empty / Loading / Error states

| **Before** | **After** |
|:--|:--|
| <img src="assets/examples/states-before.png" alt="Inconsistent empty and error states" width="100%"> | <img src="assets/examples/states-after.png" alt="Unified states from patterns.yaml" width="100%"> |
| "No data", "Error", different spinners. | Unified EmptyState / LoadingState / ErrorState with required title + description. |

### Texts / voice

| **Before** | **After** |
|:--|:--|
| "Oops! Something went wrong"<br>"Unlock seamless payments" | "Payment failed. Check your card details."<br>"No payments for this period." |

> Examples will be added after a test run on a real project. For now — the grid structure.

## Install

```bash
npx skills add ibongobe/Antislop-design-system
```

Or copy the `skills/anti-slop-ds` folder into `.claude/skills/`, `.cursor/skills/`, or the equivalent folder for your agent.

Details — in [docs/INSTALL.md](docs/INSTALL.md).

## How it works

1. The agent reads `DESIGN-RULES.md` and the templates from `templates/`.
2. Runs a short onboarding (or uses the base template if the input is empty).
3. Creates a `design-system/` folder in your project with split YAML files.
4. Any later UI generation takes only from these files. New things are added only through a proposal and confirmation.

## Docs

| File | Purpose |
|------|---------|
| [docs/ONBOARDING.md](docs/ONBOARDING.md) | Step-by-step agent onboarding |
| [docs/INPUT.md](docs/INPUT.md) | What to provide as input |
| [docs/DESIGN-RULES.md](docs/DESIGN-RULES.md) | Strict agent behavior rules |
| [docs/INSTALL.md](docs/INSTALL.md) | Installation |
| [skills/anti-slop-ds/SKILL.md](skills/anti-slop-ds/SKILL.md) | Agent instructions |
| [templates/](templates/) | YAML templates (source of truth) |

## FAQ

**How is this different from a regular anti-slop filter?**
A filter removes signs after generation. Anti-Slop DS prevents the agent from inventing — it takes only from your design system.

**What if I give nothing as input?**
The agent creates a neutral consistent system on the base template and marks values as `source: base, unconfirmed`. You can enrich it later.

**How do I add new rules and components?**
The agent proposes a change and waits for confirmation. After confirmation it updates the YAML and `DECISIONS.md`.

## License

MIT
