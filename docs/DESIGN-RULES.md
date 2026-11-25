# DESIGN-RULES.md

These rules the agent must follow when working with UI.

## Source of truth

- The single source of truth is the files in `design-system/`.
- Before generating or editing UI, read the current YAML files.
- Do not invent colors, radii, spacing, components, states, texts, or icons.
- If something is missing from YAML — stop and ask.
- **References override base**: When user provides references (screenshots, links, mockups), analyze them and derive decisions from them. The result must reflect the references, not look like current production or plain base template.

## Component etalon: HeroUI

Use [HeroUI React](https://heroui.com/en/docs/react/components) as the visual and interaction reference for standard components:

- Semantic variants (primary / secondary / tertiary / ghost / danger).
- Compound structure where it improves clarity (Card.Header / Content / Footer, etc.).
- Interactive feedback: subtle scale on press, hover states, visible accent focus rings, smooth CSS transitions.
- Surface hierarchy instead of heavy borders.
- One strong accent color.
- Accessible states and keyboard support.
- Smooth overlay enter/exit animations.

When generating or transforming UI, aim for this level of polish so the result feels modern and intentional.

## Fonts

- Use the exact font specified by the user (e.g. Roobert PRO). Put it in tokens and apply everywhere.
- Never silently fall back to system-ui or Inter if a specific font was named.

## Icons

- Default to **Tabler Icons** (outline). Use them in components and patterns where icons make sense.
- Consistent sizing.

## States

Every component and pattern must have:
- `loading`
- `empty`
- `error`

If states are missing — propose adding them.

## Cabinet / Dashboard standards

- Modals: maximum 2 buttons in the footer.
- Cards and layouts: use consistent grids, proper spacing, elevated or clearly separated cards with hierarchy.
- Goal when applying to existing project: create a visible "wow" — polished, modern, intentional UI with HeroUI-level interactivity.

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
