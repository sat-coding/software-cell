# Operating Model

A software cell is a compact product-building team made of persistent agent roles.

It should behave less like a single chatbot and more like a small studio with written state, role boundaries, and feedback loops.

## The unit of work

The unit of work is not a vague initiative.
It is a **small observable task**.

Examples:
- onboarding screen renders and navigates correctly
- signup API returns expected success/error shapes
- settings page spacing and hierarchy improved
- Android build runs on emulator without crash

Bad units of work:
- improve the app
- fix UX
- build the startup

## Team roles

### Coordinator
Owns:
- next-task selection
- scope control
- acceptance criteria
- progress checkpoints
- pause/recovery decisions

### Engineer
Owns:
- implementation
- bug fixes
- refactors
- build changes
- handing off runnable outputs

### Verifier
Owns:
- running the product
- checking whether the task actually worked
- collecting logs/screenshots/output evidence
- writing pass/fail notes

### Designer
Owns:
- screenshot review
- visual critique
- interaction polish suggestions
- hierarchy / spacing / clarity improvements

### Runtime / Ops
Owns:
- service startup
- health checks
- build environment sanity
- process recovery
- runbook maintenance

## State files

Every project should maintain a small written operating layer.

Minimum recommended files:
- `VISION.md`
- `ROADMAP.md`
- `BACKLOG.md`
- `CURRENT.md`
- `STATE.md`
- `RUNBOOK.md`
- `QA_LOG.md`
- `DECISIONS.md`
- `TEAM-PERSONALITIES.md`

These files matter because persistent systems fail when memory lives only in chat.

## Day-to-day flow

1. Coordinator selects one task from `BACKLOG.md`
2. Acceptance criteria are written into `CURRENT.md` or the task file
3. Engineer implements the change
4. Runtime/Ops ensures the product can run
5. Verifier executes the relevant checks
6. Designer reviews UI if relevant
7. Findings go into `QA_LOG.md` and `STATE.md`
8. Coordinator decides:
   - done
   - revise once more
   - defer
   - block and pause

## Artifacts over claims

The team should prefer artifacts over language.

Good:
- screenshot attached
- exact failing API response captured
- emulator build log saved
- health endpoint checked

Weak:
- should work now
- likely fixed
- seems better

## Scope discipline

The coordinator should keep loops tight.

Useful defaults:
- one primary task per cycle
- one or two active workers at a time
- no giant rewrites without evidence
- no endless retries without new signal

## Recovery rule

If the team fails twice on the same thing without new evidence:
- shrink scope
- isolate the problem
- improve observability
- or pause the loop

Do not reward churn.

## Done definition

A task is done only when:
- acceptance criteria are checked
- evidence exists
- state files are updated
- the next step is clear

If the product changed but the team state did not, the loop is incomplete.
