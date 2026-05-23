# No Fake Completion

Most agent prompts optimize for sounding helpful.

This one optimizes for being correct.

**No Fake Completion** is a hard execution policy for coding and task agents that should:
- make minimal changes
- verify before strong claims
- stop at explicit boundaries
- avoid side quests
- report blockers honestly
- stop pretending that “code changed” means “task solved”

## What this is

A reusable execution-first policy skill for:
- coding agents
- automation agents
- browser-task agents
- deployment/config agents
- operator-facing agent systems

It is not a model wrapper.
It is not an agent runtime.
It is a discipline layer.

## The problem

Most agent failures are not model failures.
They are discipline failures.

Typical failures:
- silent guessing when ambiguity matters
- overengineering simple work
- touching unrelated files
- crossing explicit phase boundaries
- claiming success without enough proof
- using weak proof for strong claims
- simulating completion when blocked

## What this policy adds

Unlike softer coding-behavior packs, this one adds explicit operational control:

- **execution-first behavior**
- **minimal-change enforcement**
- **claim ladder** (`VERIFIED` / `LIKELY FIXED` / `CHANGED ONLY`)
- **completion gate before final response**
- **phase-boundary obedience**
- **target-integrity checks**
- **anti-chaos retry and scope rules**
- **proof-surface discipline**

## The claim ladder

Most agents jump from “I changed something” to “fixed”.

This policy forces three claim levels:

- **VERIFIED** — real sufficient verification exists
- **LIKELY FIXED** — changes were made, but full proof is incomplete
- **CHANGED ONLY** — files changed, effect not confirmed

That one distinction alone cuts a lot of fake completion.

## What this policy forbids

- claiming “fixed” without verification
- using curl as browser proof
- using local success as production proof
- crossing explicit phase boundaries
- touching unrelated files
- speculative abstractions
- speculative installs
- fake progress reports
- simulated success when blocked

## Repo structure

```text
no-fake-completion/
├── README.md
├── README.ru.md
├── EXAMPLES.md
├── CLAUDE.md
├── CURSOR.md
├── LICENSE
├── skills/
│   └── no-fake-completion/
│       └── SKILL.md
├── .cursor/
│   └── rules/
│       └── no-fake-completion.mdc
└── .claude-plugin/
    ├── plugin.json
    └── marketplace.json
```

## Included surfaces

- **SKILL.md** — canonical execution policy skill
- **CLAUDE.md** — drop-in instruction file
- **Cursor rule** — `.mdc` version for Cursor
- **Examples** — before/after failures and correct behavior

## Install

### Generic skill systems
Copy `skills/no-fake-completion/SKILL.md` into your skill catalog.

### CLAUDE.md projects
Use the provided `CLAUDE.md` as a project-level instruction file.

### Cursor
Use `.cursor/rules/no-fake-completion.mdc`.

## Maintained by Riot

Maintained by **Riot** via **Riot Sermon**.

## License

MIT
