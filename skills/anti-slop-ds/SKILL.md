---
name: antislop-design-system
description: Creates and maintains a design system as the single source of truth. Removes AI slop in UI. Transforms existing interfaces into polished, consistent ones based on provided references. Uses density systems (compact/normal/airy) and a clear visual contract (DESIGN.md) with patterns and anti-patterns.
---

# Antislop Design System

You work with the design system as the single source of truth.  
When applied to an existing product (cabinets, dashboards, pages), the goal is a clear improvement: modern, consistent, intentional UI without AI slop.

**Visual contract**: Follow `DESIGN.md` for all visual and interaction decisions.  
**Density system**: User chooses compact / normal / airy. Use matching variants from `templates/systems/`.  
**Icons**:
- UI icons: **Tabler Icons** (outline) by default.
- Company / brand logos: **theSVG** (https://github.com/glincker/thesvg) — full-color and mono brand marks.
- Crypto / token logos: **cryptocurrency-icons** (https://github.com/spothq/cryptocurrency-icons) — SVG/PNG coin and token icons.
Always respect icon-text gap.

**Colors**: Soft neutrals by default. Adapt accent from user brand if given.

## Strict rules

1. Before any UI generation or edit, read `DESIGN.md`, `DESIGN-RULES.md`, and the current files in `design-system/`.
2. Take colors, radii, spacing, components, states, texts, and icons **only** from the design system. Do not invent your own.
3. If a needed value is missing — **stop and ask**.
4. All components and patterns must have states: loading, empty, error.
5. **Density first**: Assemble the system from `templates/systems/` based on chosen density.
6. Prefer soft surfaces, subtle separators, and elevation over hard borders. Use larger soft radii. Never default to tiny sharp corners or heavy outlines.
7. **References are primary**: Deeply analyze user references and override defaults where they clearly differ, while keeping the polish level of DESIGN.md.
8. **Fonts are strict**: Use the exact font specified by the user.
9. Enforce patterns and anti-patterns from `patterns.yaml` and `rules.yaml`.
10. Cabinet standards: max 2 buttons in modals, consistent grids, proper soft cards.
11. **Icons priority**:
    - UI controls, empty states, navigation, buttons → Tabler outline.
    - Company / product logos → theSVG.
    - Crypto coins and tokens → cryptocurrency-icons.
    Never use emoji or random SVGs when these libraries have the mark.

## Onboarding

Follow `docs/ONBOARDING.md`. Critical question: density (compact / normal / airy). Then assemble the system.

## Design system files

- `DESIGN.md` — visual and interaction contract
- `design-system/tokens.yaml` (and systems/)
- `design-system/components.yaml`
- `design-system/patterns.yaml`
- `design-system/rules.yaml`
- `design-system/voice.yaml`

Never generate UI outside these files.  
Result must feel intentional, consistent, and free of AI slop.
