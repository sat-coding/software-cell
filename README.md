# Software Cell

A pattern for building software with a small persistent LLM team.

This repo turns the original gist into a more complete operating model: roles, loops, validation rules, templates, and project scaffolding.

## Core idea

Most agentic coding setups stop at code generation. A software cell goes one step further:

- plan work
- implement changes
- run the product
- inspect outputs
- validate results
- document state
- decide the next move

The key claim is simple:

> The bottleneck is usually not code generation. It is closed-loop validation.

A software cell is a compact team of agents that can **build, run, inspect, and refine** a product through repeated low-speed cycles.

## Contents

### Core docs

- `software-cell.md` — main concept writeup
- `AGENCY-INTEGRATION.md` — how to use Agency Agents as the personality layer
- `TEAM-PERSONALITIES.example.md` — starter mapping for role personalities

### Operating docs

- `docs/OPERATING-MODEL.md` — how the team works day to day
- `docs/LOOPS.md` — cycle design, pacing, and stop conditions
- `docs/VALIDATION.md` — runtime validation, QA, and acceptance criteria
- `docs/RUNTIME-SURFACES.md` — how to make products observable
- `docs/MODEL-ROUTING.md` — how to split roles across stronger/weaker models

### Templates

- `templates/VISION.md`
- `templates/ROADMAP.md`
- `templates/BACKLOG.md`
- `templates/CURRENT.md`
- `templates/STATE.md`
- `templates/DECISIONS.md`
- `templates/RUNBOOK.md`
- `templates/QA_LOG.md`
- `templates/TEAM-PERSONALITIES.md`
- `templates/TASK.md`

### Example

- `examples/mobile-app-cell/` — example project skeleton for an app-oriented software cell

## Structure

A typical product using this repo would have two layers:

1. **The product repo**
   - app code
   - backend code
   - assets
   - tests

2. **The software-cell layer**
   - vision
   - backlog
   - decisions
   - runbook
   - QA log
   - current work state
   - team personalities

The software-cell layer gives the agent team durable memory and operating rules.

## Core roles

A small cell usually needs only 4-5 roles:

- **Coordinator** — planning, sequencing, scope control
- **Engineer** — implementation and debugging
- **Verifier** — testing, evidence collection, pass/fail judgment
- **Designer** — UI/UX review and polish feedback
- **Runtime/Ops** — health checks, process control, recovery

These can be implemented as separate persistent sessions or as role prompts inside one orchestrated system.

## Operating principle

Every cycle should produce an observable artifact.

Examples:
- screenshot
- build output
- test result
- log excerpt
- browser snapshot
- API response
- updated task note
- diff

Rule:

> No output without an observable artifact.

## Good fit

This pattern is especially useful for:

- web apps
- mobile apps
- internal tools
- prototype-to-product flows
- background product iteration
- long-lived side projects
- low-speed autonomous software teams

## Not the goal

This is **not** a magical startup generator.

The goal is smaller and more useful:

> a compact software team that can keep a product moving forward, slowly and reliably, with real validation.

## Suggested first setup

1. Read `software-cell.md`
2. Read `docs/OPERATING-MODEL.md`
3. Copy the files from `templates/` into your project
4. Choose a personality mapping from `AGENCY-INTEGRATION.md`
5. Write a first `BACKLOG.md` with 5-10 tasks
6. Define runtime visibility in `RUNBOOK.md`
7. Start with one small loop

## Recommended default team

- Coordinator -> Product Manager
- Engineer -> Rapid Prototyper
- Verifier -> Reality Checker
- Designer -> UI Designer
- Runtime -> DevOps Automator

See `TEAM-PERSONALITIES.example.md` and `AGENCY-INTEGRATION.md`.

## Why slow matters

A software cell should usually move slower than you expect.

Slow systems often outperform frantic ones because they:
- waste fewer tokens
- validate more carefully
- preserve context better
- retry less blindly
- generate less fake progress

The goal is not constant motion.
The goal is reliable iteration.
