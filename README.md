# ux-workflow

Скилл для Claude Code и Cursor, который ведёт UX-дизайнера через задачу по шагам: от первого запроса до handoff в разработку. Он задаёт вопросы, раскладывает ответы по файлам и помнит, на каком этапе вы остановились.

[English version below](#english)

## Зачем

На длинной UX-задаче контекст расползается: вводные в одном чате, решения в другом, результаты интервью в третьем. Через месяц уже трудно вспомнить, почему выбрали этот вариант и что делать дальше.

Скилл держит всё в папке проекта. В начале каждой сессии он читает `project-state.md` и сообщает текущий этап, статус и следующий шаг.

## Что он делает

- Создаёт структуру папок под проект и стартовые файлы.
- Ведёт по 15 этапам, не перепрыгивая вперёд без вашего подтверждения.
- Задаёт вопросы небольшими блоками и сразу сохраняет ответы в нужный файл.
- Отделяет решения от событий: «почему так решили» хранится в одном файле, хронология в другом.
- В конце сессии показывает список правок и записывает их только после подтверждения.
- Перед записью сверяет цитаты из интервью с источником дословно.
- Следит, чтобы `project-state.md` не разрастался на долгих проектах.

## Установка

```bash
npx skills add Artodocs/ux-workflow-skill
```

Или вручную:

```bash
git clone https://github.com/Artodocs/ux-workflow-skill.git
cp -R ux-workflow-skill/skills/ux-workflow ~/.claude/skills/
```

## Как пользоваться

Откройте папку проекта в Claude Code или Cursor и напишите `/ux-workflow` либо просто опишите задачу: «нужно переделать онбординг, с чего начать?».

- **Новый проект.** Скилл создаст папки и начнёт с этапа 01.
- **Продолжение.** Скилл прочитает `project-state.md` и предложит продолжить с текущего места.
- **Конец работы.** Напишите «закрываем сессию», и скилл обновит состояние, журнал и список открытых вопросов.

## 15 этапов

| # | Этап | Когда нужен |
|---|------|-------------|
| 01 | Вход в задачу | Всегда |
| 02 | Тип задачи | Всегда |
| 03 | Основание задачи | Всегда |
| 04 | Инициатор и стейкхолдеры | Всегда |
| 05 | Анализ данных и добор ответов | Всегда |
| 06 | Референсы | Внутренние всегда, внешние по желанию |
| 07 | Текущее состояние | Только при улучшении существующего |
| 08 | Цели и критерии успеха | Всегда |
| 09 | Гипотезы и варианты решения | Всегда |
| 10 | Структура решения | По сложности задачи |
| 11 | Исследование | Если гипотезы нужно проверить |
| 12 | Артефакты решения | Всегда |
| 13 | Тестирование | Если есть что тестировать |
| 14 | Handoff | Всегда |
| 15 | Итоги и знания | По необходимости |

Скилл различает четыре типа задач, и они могут сочетаться: улучшение старого, создание нового, концепт, исследование. От типа зависит, какие этапы включаются и какие вопросы задаются.

## Что появится в папке проекта

```
project-management/
  project-state.md             ← где я и что дальше
  решения-и-обоснования.md
  журнал-изменений.md

01-intake/
02-types/
03-основание-задачи/
04-стейкхолдеры/
05-analysis/
06-references/
07-current-state/
08-goals/
09-hypotheses/
10-structure/
11-research/
12-artifacts/
13-testing/
14-handoff/
15-knowledge/
16-archive/
```

Файлы внутри этапов создаются по мере работы, а не все сразу.

## Что внутри скилла

```
skills/ux-workflow/
  SKILL.md                          ← правила и порядок работы
  references/
    stages-detail.md                ← инструкции по каждому этапу
    questions-bank.md               ← вопросы для каждого этапа
    folder-structure.md             ← структура папок
    project-state-template.md       ← шаблон файла состояния
```

## Ограничения

Скилл написан на русском и ведёт все файлы проекта на русском.

## Лицензия

MIT

---

<a name="english"></a>

# ux-workflow (English)

A skill for Claude Code and Cursor that walks a UX designer through a task step by step, from the first request to developer handoff. It asks questions, files the answers where they belong, and remembers which stage you stopped at.

> The skill is written in Russian and keeps all project files in Russian. To use it in another language, translate `SKILL.md` and the files in `references/`.

## Why

On a long UX task the context scatters: the brief is in one chat, the decisions in another, the interview results in a third. A month later it is hard to recall why an option was chosen and what comes next.

The skill keeps everything in the project folder. At the start of each session it reads `project-state.md` and reports the current stage, the status and the next step.

## What it does

- Creates the project folder structure and starter files.
- Leads you through 15 stages and never skips ahead without your confirmation.
- Asks questions in small blocks and saves each answer to the right file straight away.
- Keeps decisions apart from events: the reasoning lives in one file, the timeline in another.
- At the end of a session it lists the pending edits and writes them only after you confirm.
- Checks interview quotes against the source word for word before writing them down.
- Keeps `project-state.md` from bloating on long projects.

## Install

```bash
npx skills add Artodocs/ux-workflow-skill
```

Or manually:

```bash
git clone https://github.com/Artodocs/ux-workflow-skill.git
cp -R ux-workflow-skill/skills/ux-workflow ~/.claude/skills/
```

## Usage

Open your project folder in Claude Code or Cursor and type `/ux-workflow`, or just describe the task.

- **New project.** The skill creates the folders and starts at stage 01.
- **Returning to a project.** The skill reads `project-state.md` and offers to continue where you left off.
- **End of work.** Ask it to close the session, and it updates the state, the change log and the open questions.

## The 15 stages

| # | Stage | When it applies |
|---|-------|-----------------|
| 01 | Task intake | Always |
| 02 | Task type | Always |
| 03 | Rationale for the task | Always |
| 04 | Requester and stakeholders | Always |
| 05 | Data analysis and follow-up questions | Always |
| 06 | References | Internal always, external optional |
| 07 | Current state | Only when improving something existing |
| 08 | Goals and success criteria | Always |
| 09 | Hypotheses and solution options | Always |
| 10 | Solution structure | Depends on complexity |
| 11 | Research | When hypotheses need testing |
| 12 | Solution artifacts | Always |
| 13 | Testing | When there is something to test |
| 14 | Handoff | Always |
| 15 | Outcomes and lessons | As needed |

The skill recognises four task types, which can be combined: improving something existing, building something new, a concept, and research. The type decides which stages apply and which questions are asked.

## License

MIT
