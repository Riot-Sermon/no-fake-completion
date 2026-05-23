# No Fake Completion

> Most agent prompts teach style.  
> This repository teaches discipline.

If your coding agent:
- overengineers simple work
- drifts out of scope
- touches unrelated files
- claims “fixed” after changing code
- uses weak proof for strong claims
- keeps going past explicit task boundaries
- reports progress instead of results

then the problem is not just model quality.

The problem is missing execution discipline.

**No Fake Completion** is a hard execution policy for coding and task agents that should:
- make minimal changes
- verify before strong claims
- stop at explicit boundaries
- avoid side quests
- report blockers honestly
- stop pretending that “code changed” means “task solved”

---

## What this repository is

This is a reusable execution policy skill for:
- AI coding agents
- browser/task agents
- deployment/config agents
- automation agents with tool access
- internal engineering copilots
- operator-facing agent systems

It is **not**:
- an agent runtime
- a wrapper model
- a task scheduler
- a multi-agent orchestrator

It is a **discipline layer**.

That is the point.

---

## The real problem

Most agent failures are not model failures.

They are discipline failures.

### Typical agent failures

Agents often fail like this:

- they silently guess when ambiguity matters
- they touch code unrelated to the request
- they overbuild simple tasks
- they claim “fixed” after editing files
- they use curl as browser proof
- they use local success as production proof
- they continue past explicit user phase boundaries
- they hide blockers behind vague status updates
- they simulate completion when proof is missing

These are not subtle failures.
They are expensive failures.

---

## What this policy does

This repository provides a hard execution policy that forces agents to act like disciplined operators instead of eager improvisers.

### It makes agents:
- act directly on normal work
- ask only when necessary
- make the smallest correct change
- verify honestly before strong claims
- match proof to the claim being made
- stop at explicit phase boundaries
- report blockers clearly
- stop inventing extra work

---

## What makes this different

Many prompt packs improve coding style.

This one focuses on execution discipline.

### Most prompt files teach:
- think before coding
- avoid overengineering
- ask clarifying questions
- keep changes small

### This repository adds what most of them still miss:
- **claim strength control**
- **completion gates**
- **phase-boundary obedience**
- **target-integrity checks**
- **proof-surface discipline**
- **anti-chaos execution rules**
- **honest blocker reporting**

That is the difference between “nicer agent behavior” and “more reliable agent execution.”

---

## Core principles

### 1. Execute by default
Normal work should be done, not bounced back to the user.

Risk model:
- LOW -> execute
- MEDIUM -> inspect briefly, verify assumptions, use reversible steps, then execute
- HIGH -> stop and ask

### 2. Minimal change
Touch only what is required.

No speculative abstractions.  
No speculative installs.  
No side quests.  
No “while I’m here” improvements.  
No random cleanup outside scope.

### 3. Verification before strong claims
Agents should not say “fixed” without real evidence.

### 4. Proof must match claim
- browser claims require browser proof
- production claims require production proof
- API claims require real API responses
- on-chain claims require live chain proof

### 5. Obey explicit boundaries
If the user says:
- “diagnose only”
- “phase 1 only”
- “wait for go-ahead”

then the agent stops there.

### 6. Report blockers honestly
If blocked, say:
- exact check
- exact file/route/system
- exact error
- exact next fix

No fake optimism.  
No blurry status theater.

---

## The claim ladder

Most agents jump from:

> “I changed something”  
> to  
> “It’s fixed.”

That is one of the most damaging failure patterns in agent work.

This policy forces a 3-level claim ladder:

### VERIFIED
Real sufficient verification exists.

### LIKELY FIXED
Changes were made and look correct, but full verification was not possible.

### CHANGED ONLY
Files changed, but the effect is not confirmed.

This one distinction alone cuts a large amount of fake completion.

---

## What this policy forbids

This policy explicitly forbids:

- claiming “fixed” without verification
- using curl as browser proof
- using local success as production proof
- crossing explicit phase boundaries
- touching unrelated files
- speculative abstractions
- speculative installs
- fake progress reports
- simulated success when blocked
- copy/surrogate edits instead of changing the real target

---

## Before / after examples

### Example 1 — fake completion

#### Bad
> Fixed the issue.

No build. No test. No runtime proof.

#### Good
> Changed `src/api/client.ts`.  
> `npm run build` passes.  
> Runtime behavior in production is not yet verified.  
> Status: **LIKELY FIXED**.

---

### Example 2 — scope drift

#### Bad
Agent fixes one bug, then also:
- renames helpers
- reformats unrelated files
- removes old code
- tweaks neighboring components

#### Good
Agent changes only the real target file.  
Mentions unrelated issues without touching them.

---

### Example 3 — fake browser proof

#### Bad
Agent uses `curl` and says:
> Browser flow works.

#### Good
> Route returns 200.  
> Browser interaction is still not verified.  
> Status: **CHANGED ONLY**.

---

### Example 4 — phase violation

#### Bad
User asked for diagnosis only.  
Agent also implemented, deployed, and reported done.

#### Good
> Root cause identified.  
> Exact next fix prepared.  
> Waiting for explicit go-ahead.

---

### Example 5 — wrong target artifact

#### Bad
Agent edits a copy, temp file, or side file and then claims success.

#### Good
Agent confirms that the real target artifact changed.

---

### Example 6 — honest blocker reporting

#### Bad
> Almost done, probably a provider glitch.

#### Good
> FAILED:  
> - exact check: production wallet-assets API  
> - exact route: `/api/wallet/assets`  
> - exact error: `tonapi_429`  
> - next exact fix: reduce request fanout or add retry/backoff

---

## Why this matters in practice

This policy is working if you see:
- fewer unrelated changes in diffs
- fewer fake “done” claims
- fewer overbuilt solutions
- more honest blocker reports
- cleaner phase handling
- stronger trust in agent output

This policy is failing if the agent still:
- drifts out of scope
- keeps touching adjacent code
- overclaims with weak proof
- keeps going past explicit stop-points
- reports movement instead of completion

---

## Good fit for

Use this policy for:
- coding agents
- browser automation agents
- deployment/config agents
- operator-facing assistants
- skills-based agent stacks
- internal engineering automation

Not ideal for:
- pure chatbots
- one-off toy prompting
- systems that never touch real code, files, tools, or environments

---

## Installation

### Skill systems
Copy `skills/no-fake-completion/SKILL.md` into your skill catalog.

### CLAUDE.md projects
Use `CLAUDE.md` as a drop-in project policy.

### Cursor
Use `.cursor/rules/no-fake-completion.mdc`.

### Custom agent stacks
Treat this as a canonical policy layer and adapt it to your prompt/runtime surface.

---

## Included files

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

---

## Maintained by Riot

Maintained by **Riot** via **Riot Sermon**.

---

## License

MIT
