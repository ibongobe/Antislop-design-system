# DESIGN-RULES.md

These rules the agent must follow when working with UI.

## Source of truth

- The single source of truth is `DESIGN.md` + files in `design-system/`.
- Before generating or editing UI, read them.
- Do not invent colors, radii, spacing, components, states, texts, or icons.
- If something is missing — stop and ask.
- **References override base rigidly**: When user provides references, analyze them deeply and derive decisions from them. The result must reflect the reference while keeping the polish level of DESIGN.md.

## Visual direction

- Soft surfaces and hierarchy instead of heavy borders.
- Larger, softer radii (never tiny sharp corners).
- Subtle elevation over outlines.
- One strong accent color.
- Semantic variants (primary / secondary / tertiary / ghost / danger).
- Accessible states and visible focus.
- Consistent spacing from the density system.

## Fonts

- Use the exact font specified by the user.
- Never silently fall back to system fonts if a specific font was named.

## Icons

- Default to **Tabler Icons** (outline).
- Consistent sizing.
- Always keep at least `icon_text_gap` between icon and text. Never let them stick together.

## Spacing

- Use the density system consistently.
- Enforce icon-text gap, card padding, stack gaps, section gaps.
- Never allow random spacing or sticking elements.

## States

Every component and pattern must have:
- `loading`
- `empty`
- `error`

## Cabinet / Dashboard standards

- Modals: maximum 2 buttons in the footer.
- Cards and layouts: consistent grids, proper spacing, soft elevated cards.
- Goal: visible improvement — polished, intentional UI that follows the user's reference and DESIGN.md.

## Forbidden

- Generating UI outside of the design system.
- Inventing values.
- Ignoring anti-patterns.
- Creating components without states.
- Ignoring user-specified font or provided references.
- 3+ buttons in modals.
- Hard heavy borders and tiny sharp radii.
- Icons sticking to text.
- Inconsistent spacing.
- Flat ugly cards without hierarchy.
- AI-slop copy.

Follow DESIGN.md for all visual decisions.
