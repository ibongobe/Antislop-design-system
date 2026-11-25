<div align="center">

# Anti-Slop DS

Создай свою дизайн-систему и избавься от нейрослопа в проектах с AI-агентами.

<code>npx skills add ibongobe/Antislop-design-system</code>

[Install](#install) · [Before / After](#before--after) · [How it works](#how-it-works) · [Docs](#docs)

</div>

---

**Anti-Slop DS** даёт агенту единственный источник правды — твою дизайн-систему в YAML. Агент берёт цвета, радиусы, компоненты, состояния и тексты только оттуда. Если чего-то нет — останавливается и спрашивает, а не придумывает.

Это не фильтр после факта. Это источник правды, который агент читает перед каждой генерацией UI.

## Before / After

Примеры будут добавлены после тестовых прогонов на реальных проектах. Снизу — структура сетки, которая будет заполняться.

### UI

| **Before: без Anti-Slop DS** | **After: Anti-Slop DS** |
|:--|:--|
| <img src="assets/examples/ui-before.png" alt="Нейрослоп: разные цвета, случайные радиусы, No data" width="100%"> | <img src="assets/examples/ui-after.png" alt="Консистентный интерфейс из дизайн-системы" width="100%"> |
| Разные цвета на экранах, случайные радиусы, «No data», кнопки разного размера. | Всё из YAML: одни цвета, радиусы, состояния, тексты. Агент не придумывает. |

### Empty / Loading / Error states

| **Before** | **After** |
|:--|:--|
| <img src="assets/examples/states-before.png" alt="Разные empty и error на экранах" width="100%"> | <img src="assets/examples/states-after.png" alt="Единые состояния из patterns.yaml" width="100%"> |
| «No data», «Error», разные спиннеры. | Единые EmptyState / LoadingState / ErrorState с обязательными title + description. |

### Тексты / voice

| **Before** | **After** |
|:--|:--|
| «Упс! Что-то пошло не так»<br>«Unlock seamless payments» | «Платёж не прошёл. Проверьте данные карты.»<br>«Пока нет платежей за этот период.» |

> Примеры будут добавлены после тестового прогона на реальном проекте. Пока — структура сетки.

## Install

```bash
npx skills add ibongobe/Antislop-design-system
```

Или скопируй папку `skills/anti-slop-ds` в `.claude/skills/`, `.cursor/skills/` или аналогичную папку агента.

Подробнее — в [docs/INSTALL.md](docs/INSTALL.md).

## How it works

1. Агент читает `DESIGN-RULES.md` и шаблоны из `templates/`.
2. Проводит короткий онбординг (или берёт базовый шаблон, если вход пустой).
3. Создаёт в проекте папку `design-system/` с разбитыми YAML.
4. Дальше любая генерация UI идёт только из этих файлов. Новое добавляется только через предложение и подтверждение.

## Docs

| Файл | Назначение |
|------|------------|
| [docs/ONBOARDING.md](docs/ONBOARDING.md) | Пошаговый онбординг агента |
| [docs/INPUT.md](docs/INPUT.md) | Что дать на вход |
| [docs/DESIGN-RULES.md](docs/DESIGN-RULES.md) | Жёсткие правила поведения |
| [docs/INSTALL.md](docs/INSTALL.md) | Установка |
| [skills/anti-slop-ds/SKILL.md](skills/anti-slop-ds/SKILL.md) | Инструкция для агента |
| [templates/](templates/) | Шаблоны YAML (источник правды) |

## FAQ

**Чем отличается от обычного антислоп-фильтра?**
Фильтр убирает признаки после генерации. Anti-Slop DS не даёт агенту придумывать — он берёт только из твоей дизайн-системы.

**Что будет, если ничего не дать на вход?**
Агент создаст нейтральную консистентную систему на базовом шаблоне и пометит значения как `source: base, unconfirmed`. Позже её можно обогащать.

**Как добавлять новые правила и компоненты?**
Агент предлагает изменение и ждёт подтверждения. После подтверждения обновляет YAML и `DECISIONS.md`.

## Лицензия

MIT
