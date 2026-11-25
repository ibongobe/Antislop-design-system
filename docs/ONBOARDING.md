# Anti-Slop DS Onboarding

If the project does not have a `design-system/` folder — start with onboarding. Ask questions one or two at a time. Do not generate the interface until you get the minimum or an explicit "do it on the base template".

## Stage 0. Context

1. What is the product? (dashboard, admin, B2C site, etc.)
2. On which platforms? (web, mobile web, iOS, Android)
3. Are there already screens / mockups / references?

## Stage 1. Brand and visual

4. Are there brand colors? (hex or "no, pick neutral")
5. Are there fonts? (name or "system")
6. Interface density? (compact / normal / airy)

## Stage 2. Key entities

7. What are the main entities? (for example: payments, users, tasks)
8. What are the 3–5 most important screens?

## Stage 3. Showcase

9. Where to build the design system showcase?
   - Figma
   - Storybook
   - Both
   - Not needed yet

## Stage 4. Assembly

After the answers, create in the project:

```
design-system/
  tokens.yaml
  components.yaml
  patterns.yaml
  rules.yaml
  voice.yaml
DESIGN-RULES.md
DECISIONS.md
```

Copy the structure from `templates/` and fill in known values. Mark everything unknown as `source: base, unconfirmed`.

In `DECISIONS.md` list what still needs to be clarified.

## Behavior on empty input

If the user says "just do it" or skips questions:

- Use the base templates.
- Mark everything as `source: base, unconfirmed`.
- In the final message list what should be clarified so the system becomes product-specific.
