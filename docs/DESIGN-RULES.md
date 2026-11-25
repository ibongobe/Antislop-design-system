# DESIGN-RULES.md

These rules the agent must follow when working with UI.

## Source of truth

- The single source of truth is the files in `design-system/`.
- Before generating or editing UI, read the current YAML files.
- Do not invent colors, radii, spacing, components, states, or texts.
- If something is missing from YAML — stop and ask.

## States

Every component and pattern must have:
- `loading`
- `empty`
- `error`

If states are missing — propose adding them.

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
