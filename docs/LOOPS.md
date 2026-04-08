# Loops

The software cell works through repeated small loops.

The loop is the core behavior of the team.

## Standard loop

1. Pick one small task
2. Clarify acceptance criteria
3. Implement
4. Run
5. Observe
6. Verify
7. Record
8. Decide next move

This can be written more compactly as:

**plan -> build -> run -> inspect -> decide**

## Why loops matter

Without a loop, the team becomes one of two bad things:
- endless planning
- endless coding

The loop forces contact with reality.

## Cadence

The cell should generally move at a low, controlled pace.

Suggested default cadence:
- one meaningful task per cycle
- one or two active workers
- periodic human-visible checkpoints
- explicit pause conditions

## Pause conditions

The loop should stop when:
- credentials are missing
- emulator/device/runtime is unavailable
- the environment is broken
- repeated failures produce no new information
- no observable progress was made
- budget/time cap is reached
- human direction changed

## Anti-churn rule

Do not retry the same failure mode without changing one of:
- scope
- instrumentation
- runtime visibility
- approach
- test condition

## Output rule

Every cycle must leave at least one artifact:
- screenshot
- test output
- build log
- API response
- browser snapshot
- diff
- QA note
- updated task state

No artifact, no progress.

## Review gate

Before starting the next cycle, ask:
- what changed?
- what was observed?
- what remains uncertain?
- what is the smallest next move?

## Long loops

Long-running autonomous loops are only useful when they have control surfaces.

A long loop should define:
- objective
- stop condition
- checkpoint cadence
- quality gate
- recovery action after repeated failure

Otherwise it is just expensive wandering.
