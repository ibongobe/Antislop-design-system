# DESIGN.md

Visual and interaction contract for the Antislop Design System.

Use this file as the source of truth for how interfaces should look and feel.  
All generated UI must follow these rules. Product-specific tokens live in `design-system/` YAML files.

## Design Direction

- Build calm, modern interfaces with clear content hierarchy.
- Prefer whitespace, typography, and surface levels over decoration and hard borders.
- Use one strong accent for primary actions. Reserve status colors for meaning only.
- Soft surfaces and subtle elevation over heavy outlines.
- Consistent spacing and radii. Never mix systems on one screen.
- Accessible, keyboard-friendly, visible focus states.
- Icons:
  - UI icons: Tabler Icons (outline) by default.
  - Company / brand logos: theSVG (https://github.com/glincker/thesvg).
  - Crypto / token logos: cryptocurrency-icons (https://github.com/spothq/cryptocurrency-icons).
  Always keep gap between icon and text.

## Light Glass Effect

Use a subtle glass / frosted look on elevated surfaces when it adds polish (cards, modals, dropdowns, floating panels).

Recommended implementation (lightweight, works everywhere):
- `backdrop-filter: blur(12px)` to `blur(20px)`
- Semi-transparent background: `rgba(255,255,255,0.7)` or `rgba(255,255,255,0.85)` in light mode
- Soft border: `1px solid rgba(255,255,255,0.4)` or very light separator
- Optional very light shadow for depth

Keep it light. Do not overuse. Prefer on overlays and key cards, not on every surface. Respect reduced-motion and performance.

## Colors

Use semantic tokens. Do not hardcode random hex values.

| Role              | Purpose                              | Notes                          |
|-------------------|--------------------------------------|--------------------------------|
| background        | Page / canvas background             | Soft neutral                   |
| surface           | Cards, panels, elevated areas        | Usually white or near-white    |
| surface-secondary | Nested or lower-emphasis regions     | Slightly darker than surface   |
| text-primary      | Main content                         | High contrast                  |
| text-secondary    | Supporting text, muted               | Lower contrast                 |
| border / separator| Subtle boundaries                    | Soft, never harsh black        |
| accent            | Primary actions, focus, emphasis     | One strong color               |
| success / warning / danger | Status only                 | Semantic, not decorative       |

Prefer soft neutrals. Adapt accent from user brand if provided, keep neutral structure consistent.

## Typography

- Use the exact font specified by the user.
- Clear hierarchy: headings in sentence case, comfortable line height.
- Primary text = text-primary, supporting = text-secondary.
- Avoid all-caps except short established labels.

## Spacing

- 4px base rhythm.
- Use the density system (compact / normal / airy) consistently.
- Enforce icon-text gap (never stick icons to text).
- Consistent card padding, section gaps, stack gaps.

## Radius

- Soft, modern radii. Avoid tiny sharp corners.
- Base around 8px, larger for cards and fields.
- Use the density variant. Nested elements usually slightly smaller radius than parent.

## Elevation

- Prefer subtle shadows or surface levels for hierarchy.
- Avoid heavy hard borders.
- Cards and raised content use light elevation.
- Overlays (modals, dropdowns) use stronger elevation.
- Optional light glass (backdrop blur + transparency) on key elevated surfaces.

## Components & Patterns

- Semantic variants: primary / secondary / tertiary / ghost / danger.
- Maximum one primary action per context.
- Modals: max 2 buttons in footer. Prefer light glass background.
- Cards: consistent padding, soft elevation or subtle border, clear hierarchy, grid layouts. Light glass optional on featured cards.
- Lists, tables, forms: consistent spacing and states.
- Every component and pattern must have loading / empty / error states.

## Redesign rules

- When redesigning an existing page, **preserve all UX elements**. Keep every functional control, action, data point, and piece of information. Restyle and improve hierarchy, but do not remove or hide anything functional.
- You may suggest UX improvements based on heuristics (e.g. reduce modal buttons to 2, group lists longer than 7±2 items, clarify primary action). Present them as recommendations.

## Interaction

- Visible focus ring (accent color).
- Subtle feedback on hover and press.
- Smooth transitions. Respect reduced motion.
- Disabled state clearly visible.

## Do

- Use semantic tokens and the density system.
- Establish hierarchy with spacing, type, and surface levels.
- Keep one strong accent.
- Use Tabler for UI icons, theSVG for company logos, cryptocurrency-icons for crypto tokens. Always with proper gap.
- Apply light glass sparingly for polish on cards and overlays.
- Preserve all existing UX elements when redesigning.
- Suggest UX improvements when obvious issues exist (but do not apply them silently).
- Follow user references when provided, but keep this polish level.

## Don't

- Hard heavy borders and tiny sharp radii.
- Icons sticking to text.
- Three or more buttons in a modal footer.
- Random spacing or mixed radius systems.
- Invented colors, fonts, or components outside the design system.
- Flat ugly cards without hierarchy.
- AI-slop phrases ("Unlock the power of", "Seamless experience").
- Ignoring user-specified font or provided references.
- Using emoji or random SVGs for logos when theSVG or cryptocurrency-icons have them.
- Overusing heavy glass or refraction effects that hurt performance or readability.
- Removing or hiding existing functional UX elements during redesign.

This contract + the YAML files in `design-system/` are the single source of truth.
