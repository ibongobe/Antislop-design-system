# Antislop Design System Onboarding

If the project does not have a `design-system/` folder — start with onboarding. Ask questions one or two at a time.

**Critical**: Density choice drives the entire system.

## Stage 0. Context

1. What is the product?
2. Platforms?
3. Existing screens / mockups / references?

## Stage 1. Brand and visual

4. Brand colors? (hex or "no, pick / match closest from Mobbin")
5. Font? (exact name, e.g. Roobert PRO)
6. **Interface density?** (compact / normal / airy) — this selects the full system of radii, spacing, type scale, cards, layouts.

## Stage 2. Tone of Voice

7–9. TOV, terms, good/bad examples.

## Stage 3. Key entities

10–11. Main entities and screens.

## Stage 4. Showcase

12. Where to build showcase?

## Stage 5. Assembly

After density is known:

1. Copy matching variants from `templates/systems/` (radius, spacing, typography, colors, cards, layouts).
2. Merge into project `design-system/`.
3. Apply color matching logic if user gave hex.
4. Mark unconfirmed values.
5. Create DESIGN-RULES.md and DECISIONS.md.

Result should be a coherent, density-aware design system that feels intentional.
