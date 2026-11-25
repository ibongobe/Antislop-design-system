# DESIGN-RULES.md

These rules the agent must follow when working with UI.

## Source of truth

- The single source of truth is the files in `design-system/`.
- Before generating or editing UI, read the current YAML files.
- Do not invent colors, radii, spacing, components, states, texts, or icons.
- If something is missing from YAML — stop and ask.
- **References override base rigidly**: When user provides references (screenshots, links, mockups), analyze them deeply and derive decisions **directly** from them. The result must match the style of the reference, not look like current production or plain base template.

## Component etalon: HeroUI

Use [HeroUI React](https://heroui.com/en/docs/react/components) as the visual and interaction reference for standard components:

- Semantic variants (primary / secondary / tertiary / ghost / danger).
- Compound structure where it improves clarity.
- Interactive feedback: subtle scale on press, hover states, visible accent focus rings, smooth CSS transitions.
- Surface hierarchy instead of heavy borders.
- One strong accent color.
- Accessible states and keyboard support.
- Smooth overlay enter/exit animations.

**Color palette**: For backgrounds and neutral shades use HeroUI-inspired oklch values (background, surface, surface-secondary, muted, border) unless the user's reference defines otherwise. Put them in tokens.yaml.

## Fonts

- Use the exact font specified by the user (e.g. Roobert PRO). Put it in tokens and apply everywhere.
- Never silently fall back to system-ui or Inter if a specific font was named.

## Icons

- Default to **Tabler Icons** (outline). Use them in components and patterns where icons make sense.
- Consistent sizing.
- **Always** keep at least `icon_text_gap` (default 8px) between icon and text. Never let them stick together.

## Spacing

- Immediately establish spacing rules in tokens.yaml.
- Use the scale consistently.
- Enforce icon-text gap, card padding, stack gaps, section gaps.
- Never allow elements to stick or have random spacing.

## States

Every component and pattern must have:
- `loading`
- `empty`
- `error`

If states are missing — propose adding them.

## Cabinet / Dashboard standards

- Modals: maximum 2 buttons in the footer.
- Cards and layouts: use consistent grids, proper spacing, elevated or clearly separated cards with hierarchy.
- Goal when applying to existing project: create a visible "wow" — polished, modern, intentional UI with HeroUI-level interactivity that rigidly follows the user's reference style.

## Changes

- New rules, colors, anti-patterns, and recommendations are fixed only by updating YAML.
- Always propose the change and wait for confirmation (unless otherwise specified in `change_policy`).
- After confirmation update the corresponding file and `DECISIONS.md`.

## Empty input

Use the base templates from the Antislop Design System repository and mark values as `source: base, unconfirmed`.

## Forbidden

- Generating UI outside of `design-system/`.
- Inventing "similar" values.
- Ignoring `never` and `anti_patterns`.
- Creating components without states.
- Ignoring user-specified font or provided references.
- Putting 3+ buttons in modals.
- Producing flat, inconsistent, production-like UI when transforming an existing cabinet.
- Missing interactive feedback (hover, press scale, focus ring) on interactive elements.
- Icons sticking to text (missing gap).
- Inconsistent or missing spacing rules.
