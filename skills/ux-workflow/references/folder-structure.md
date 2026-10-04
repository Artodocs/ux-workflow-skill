# Инициализация структуры UX-проекта

## Команды для создания структуры папок

Запусти в корне проекта:

```bash
# Управление проектом
mkdir -p project-management

# Этапы процесса
mkdir -p 01-intake
mkdir -p 02-types
mkdir -p 03-основание-задачи
mkdir -p 04-стейкхолдеры
mkdir -p 05-analysis
mkdir -p 06-references/screenshots
mkdir -p 06-references/docs
mkdir -p 07-current-state
mkdir -p 08-goals
mkdir -p 09-hypotheses
mkdir -p 10-structure
mkdir -p 11-research
mkdir -p 12-artifacts
mkdir -p 13-testing
mkdir -p 14-handoff
mkdir -p 15-knowledge
mkdir -p 16-archive
```

## Создание стартовых файлов

```bash
# Управление
touch project-management/project-state.md
touch project-management/решения-и-обоснования.md
touch project-management/журнал-изменений.md

# Этап 03
touch 03-основание-задачи/основание-задачи.md

# Этап 04
touch 04-стейкхолдеры/инициатор-и-стейкхолдеры.md

# Этап 06
touch 06-references/внутренние-референсы.md
touch 06-references/внешние-референсы.md
```

## Файлы, создаваемые по мере работы (не сразу)

| Файл | Когда создавать |
|------|----------------|
| `01-intake/бриф-задачи.md` | Этап 01 |
| `01-intake/инсайты.md` | Этап 01 |
| `02-types/тип-задачи.md` | Этап 02 |
| `07-current-state/как-работает-сейчас.md` | Только «улучшение-старого» |
| `08-goals/цель-задачи.md` | Этап 08 |
| `09-hypotheses/гипотезы.md` | Этап 09 |
| `10-structure/структура-решения.md` | По необходимости |
| `11-research/план-исследования.md` | Этап 11 |
| `12-artifacts/список-артефактов.md` | Этап 12 |
| `13-testing/план-тестирования.md` | Этап 13 |
| `14-handoff/передача-в-разработку.md` | Этап 14 |
| `project-management/итоги-проекта.md` | При необходимости |

## Полная структура (для проверки)

```
project-management/
  project-state.md
  решения-и-обоснования.md
  журнал-изменений.md
  итоги-проекта.md              ← при необходимости

01-intake/
02-types/
03-основание-задачи/
  основание-задачи.md
04-стейкхолдеры/
  инициатор-и-стейкхолдеры.md
05-analysis/
06-references/
  внутренние-референсы.md
  внешние-референсы.md
  screenshots/
  docs/
07-current-state/               ← только для "улучшение-старого"
08-goals/
09-hypotheses/
10-structure/                   ← по необходимости
11-research/
12-artifacts/
13-testing/
14-handoff/
15-knowledge/
16-archive/
```
