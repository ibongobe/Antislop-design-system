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
- Tabler Icons (outline) by default. Always keep gap between icon and text.

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

## Components & Patterns

- Semantic variants: primary / secondary / tertiary / ghost / danger.
- Maximum one primary action per context.
- Modals: max 2 buttons in footer.
- Cards: consistent padding, soft elevation or subtle border, clear hierarchy, grid layouts.
- Lists, tables, forms: consistent spacing and states.
- Every component and pattern must have loading / empty / error states.

## Interaction

- Visible focus ring (accent color).
- Subtle feedback on hover and press.
- Smooth transitions. Respect reduced motion.
- Disabled state clearly visible.

## Do

- Use semantic tokens and the density system.
- Establish hierarchy with spacing, type, and surface levels.
- Keep one strong accent.
- Use Tabler icons with proper gap.
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

This contract + the YAML files in `design-system/` are the single source of truth.
