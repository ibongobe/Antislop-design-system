# Установка

## Через skills (рекомендуется)

```bash
npx skills add ibongobe/Antislop-design-system
```

Работает с Claude Code, Cursor, Codex, Cline и другими агентами, которые поддерживают Agent Skills.

## Вручную

Скопируй папку `skills/anti-slop-ds` в:

- Claude Code: `.claude/skills/`
- Cursor: `.cursor/skills/`
- Или в глобальную папку скиллов агента

## После установки

Скажи агенту:

> Запусти Anti-Slop DS. Проведи онбординг и создай дизайн-систему в проекте.

Агент прочитает `SKILL.md`, проведёт онбординг и создаст папку `design-system/` с разбитыми YAML-файлами.
