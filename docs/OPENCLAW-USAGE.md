# OpenClaw Usage

This document explains how to run the software-cell pattern inside OpenClaw.

## Mental model

OpenClaw already gives you the primitives needed for a software cell:

- persistent sessions
- subagents / ACP sessions
- browser/runtime tooling
- filesystem-based memory
- messaging and async completion
- workspace-local operating files

So the job is not to invent a new runtime.
It is to define a repeatable operating pattern on top of OpenClaw.

## Recommended role mapping in OpenClaw

### Main session = Coordinator
Use the main session as the highest-context coordinator.

Responsibilities:
- understand human intent
- keep scope sane
- choose next task
- route work to workers
- review results
- decide whether to continue, pause, or redirect

### Worker sessions = Specialists
Use spawned sessions for role-specific execution.

Typical workers:
- engineer-worker
- verifier-worker
- design-worker
- runtime-worker

For heavier coding loops, prefer spawned sessions so the main session stays clean.

## Suggested model split

A practical OpenClaw setup:

- Main session / coordinator / difficult reasoning -> stronger model
- Implementation / repetitive coding / long loops -> cheaper model
- Final review -> stronger model again if needed

This preserves quality while controlling burn.

## Filesystem state

Keep the software-cell docs inside the product repo or in a sibling operations directory.

Recommended files:
- `VISION.md`
- `ROADMAP.md`
- `BACKLOG.md`
- `CURRENT.md`
- `STATE.md`
- `RUNBOOK.md`
- `QA_LOG.md`
- `DECISIONS.md`
- `TEAM-PERSONALITIES.md`

These are the durable state of the team.

## Typical OpenClaw cycle

1. Human gives direction
2. Main session updates `CURRENT.md`
3. Main session spawns worker(s)
4. Engineer makes changes
5. Runtime/Verifier runs the product
6. Browser/canvas/logs/screenshots are collected
7. Findings are written back to files
8. Main session decides next move

## Good use of sessions

Use spawned sessions when:
- coding is multi-step
- context would otherwise bloat the main thread
- you want a persistent role identity
- you want slower autonomous progress in the background

Avoid unnecessary spawning when:
- the task is a one-file edit
- no runtime validation is needed
- the work is simpler inline

## Runtime tools in OpenClaw

The software cell should lean on first-class tools:

- `browser` for web UI validation
- `canvas` for rendered surfaces when available
- `exec` for local commands, builds, logs, tests
- `sessions_spawn` for persistent workers
- `memory_*` for durable recall when decisions/preferences matter

## Suggested worker labels

Examples:
- `software-cell-engineer`
- `software-cell-verifier`
- `software-cell-design`
- `software-cell-runtime`

Labels should be stable if you want to keep a persistent team identity.

## Checkpoint pattern

After each meaningful cycle, update at least:
- `CURRENT.md`
- `STATE.md`
- `QA_LOG.md` if validation happened
- `DECISIONS.md` if a real tradeoff was chosen

## Important rule

Do not let worker conclusions live only inside session history.
If it matters, write it to files.

## Practical example

A web app improvement loop might look like this:

1. Coordinator selects task: improve onboarding CTA layout
2. Engineer worker edits UI files
3. Runtime worker starts dev server
4. Verifier opens browser snapshot and checks flow
5. Designer comments on screenshot quality
6. Coordinator updates task state and decides whether to iterate again

This is the software-cell pattern running natively inside OpenClaw.
