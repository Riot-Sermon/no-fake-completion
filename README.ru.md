# No Fake Completion

Большинство агентных промптов учат модель выглядеть полезной.

Этот репозиторий учит её быть точной.

**No Fake Completion** — это жёсткий execution-first policy skill для coding/task agents, который заставляет агента:
- делать минимальные изменения
- проверять результат до сильных claim'ов
- останавливаться на явных границах фаз
- не уходить в side quests
- честно сообщать блокеры
- не путать «код изменён» с «задача реально решена»

## Что это такое

Это не runtime и не framework.
Это слой дисциплины для агентов.

Подходит для:
- coding agents
- automation agents
- browser-task agents
- deploy/config agents
- operator-facing agent systems

## В чём проблема

Большая часть косяков агентов — это не модельные косяки, а косяки дисциплины.

Типичные провалы:
- молчаливые догадки при важной неоднозначности
- overengineering простых задач
- лишние изменения вне scope
- нарушение phase boundaries
- ложный claim “fixed” без достаточной проверки
- слабое доказательство для сильного claim
- симуляция completion, когда задача заблокирована

## Что добавляет этот policy

В отличие от мягких coding-guideline паков, здесь есть:

- **execution-first поведение**
- **жёсткий minimal-change подход**
- **claim ladder** (`VERIFIED` / `LIKELY FIXED` / `CHANGED ONLY`)
- **completion gate перед финальным ответом**
- **phase-boundary obedience**
- **target-integrity checks**
- **anti-chaos правила**
- **proof-surface discipline**

## Что этот policy запрещает

- писать “fixed” без проверки
- выдавать curl за browser proof
- выдавать local success за production proof
- переходить границы явной фазы
- трогать несвязанные файлы
- добавлять speculative abstractions
- делать speculative installs
- симулировать progress
- симулировать success при блокере

## Maintained by Riot

Поддерживается **Riot** через **Riot Sermon**.

## License

MIT
