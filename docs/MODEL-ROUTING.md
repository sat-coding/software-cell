# Model Routing

Not every task in a software cell needs the strongest model.

A good software cell routes work by role and difficulty.

## High-end model

Use the strongest model for:
- planning
- architecture
- prioritization
- hard debugging
- quality review
- difficult tradeoff decisions
- final synthesis

## Cheaper/faster model

Use a cheaper or faster model for:
- implementation
- repetitive coding
- routine refactors
- file updates
- structured backlog cleanup
- repeated QA execution steps

## Practical split

A useful default is:
- strongest model = coordinator + final reviewer
- cheaper model = engineer + repetitive verifier work

## Why this works

Coding loops often burn most tokens in repetition, not insight.

If you reserve the strongest model for decisions and use a cheaper one for routine execution, you preserve quality where it matters and reduce cost where it does not.

## Warning

Do not over-fragment the team just because multiple models are available.

More workers is not automatically better.
The goal is controlled progress, not parallel chaos.
