# A pattern for building software with an LLM team

This is an idea file. It is designed to be copy-pasted into your own LLM agent (OpenClaw, Codex, Claude Code, OpenCode / Pi, or etc.). Its goal is to communicate the high-level pattern. The exact implementation should be worked out between you and the agent.

Most people's experience with LLMs and software looks like this: they ask for a feature, the model writes some code, maybe fixes a bug, maybe answers a question, and then the interaction ends. On the next task the process starts over. There is no stable team, no durable process, no operational memory beyond chat history and repo state. The model behaves more like an on-demand contractor than a software company.

The idea here is different.

Instead of using one LLM as a stateless coding assistant, you use a small set of LLM roles as a persistent software team. The team does not just write code. It plans work, implements features, runs the product, observes the result, verifies what actually happened, documents state, and decides the next move. It works in small controlled cycles. The output is not only code — it is a continuously operating product-building loop.

This is the key difference: the artifact is not just the repository. The artifact is the **working development system around the repository**. A software cell. A small autonomous team with memory, roles, runtime visibility, and feedback loops.

You are not trying to create a magical agent that "builds the whole startup." That framing is too vague and too expensive. You are trying to create a compact team that can keep moving a product forward at low speed, with real validation, without constant supervision.

The core insight is that coding is not the bottleneck. **Closed-loop validation is.**

A team that only writes code is not a team. It is autocomplete with delusions. A real software team has to be able to answer:

- Did the thing run?
- What did it look like?
- What broke?
- What did the logs say?
- Did the UX improve or get worse?
- Is the current result worth keeping?
- What should happen next?

Without this, the agents are blind. They produce activity, not progress.

There are a few layers.

## The repository

This is the product itself. App code, backend code, scripts, assets, tests. Standard software project stuff.

## The team state

This is a directory of markdown files that defines how the software team operates. For example:

- `VISION.md` — what the product is trying to become
- `ROADMAP.md` — the major phases and milestones
- `BACKLOG.md` — the current task pool
- `CURRENT.md` — what is being worked on right now
- `QA_LOG.md` — what was run, what passed, what broke
- `DECISIONS.md` — important technical and product decisions
- `RUNBOOK.md` — how to run, test, inspect, and recover the product
- `STATE.md` — current team status and recent progress
- `ROLES.md` — who does what inside the agent team

This layer is critical. The agents need shared working memory that lives in files, not only in chat context.

## The runtime surface

Every serious software loop needs a way to observe the product. This is not optional.

For a web app, that might be:

- local server
- browser snapshot
- console logs
- screenshots

For an Android app:

- emulator or device
- build output
- screenshots
- runtime logs
- crash traces

For a backend:

- health endpoints
- test output
- logs
- API responses

If the team cannot run the product and inspect the result, it cannot really improve it. It can only speculate.

So a good software cell always defines one explicit question:

**How will the team observe whether the product actually works?**

That answer becomes part of the runbook.

## The roles

You do not need ten agents. Usually four or five is enough.

### Coordinator

Owns planning, sequencing, task slicing, and overall pace. Chooses the next unit of work. Prevents chaos.

### Engineer

Implements the change. Writes code. Refactors. Fixes bugs.

### Verifier

Runs the product, tests flows, checks logs, records whether the result is actually working.

### Designer

Looks at screenshots or UI outputs and comments on clarity, layout, hierarchy, friction, and polish.

### Runtime / Ops

Keeps the system executable. Starts services, checks health, restarts failed processes, manages the environment.

These do not all have to be separate processes. Sometimes one model can play multiple roles. The important part is that the responsibilities exist.

## The cycle

The team works in short cycles, not open-ended marathons.

A typical cycle looks like this:

1. Pick one small task
2. Clarify acceptance criteria
3. Implement the change
4. Run the product
5. Observe the result
6. Verify against criteria
7. Record outcome in files
8. Decide whether to keep, revise, or defer

This is the whole game.

Not:

- brainstorm endlessly
- rewrite architecture every loop
- spawn five agents to argue abstractly
- generate giant plans nobody executes

Just:

**plan -> build -> run -> inspect -> decide**

That is what makes it feel like a real software team.

## Acceptance criteria

Every task should have observable completion conditions.

Bad:

- "improve onboarding"
- "make UI better"
- "work on Android app"

Good:

- onboarding screen renders without crash
- CTA button navigates correctly
- screen works on emulator
- no console or runtime errors during flow
- screenshot shows improved spacing and visual hierarchy
- build passes
- feature is documented in `QA_LOG.md`

The more observable the task, the more autonomous the team can be.

## Validation is the center

Most agent systems over-invest in planning and under-invest in validation.

The verifier role is the difference between:

- "I think this works"

and

- "I ran it, saw it, and here is what happened"

This is why screenshots, logs, browser snapshots, health checks, and test results matter so much. The team needs artifacts from reality, not just language.

A useful rule is:

**No output without an observable artifact.**

A cycle should leave behind at least one of these:

- screenshot
- test result
- build output
- log excerpt
- live URL
- API response
- diff
- issue note
- acceptance check result

This keeps the loop grounded.

## Pace matters

A software cell should usually move slowly.

This sounds counterintuitive, but slow systems often outperform frantic ones because they:

- waste fewer tokens
- retry failures less blindly
- preserve context better
- validate more carefully
- avoid fake progress

You do not need a team that works every minute. You need a team that works **reliably**.

A good default is:

- one small task per cycle
- one or two workers at a time
- periodic checkpoints
- explicit pause conditions
- persistent written state

This makes the system sustainable.

## Model split

Not every role needs the strongest model.

A useful setup is:

- strongest model for planning, architecture, prioritization, and final review
- cheaper or faster model for implementation, repetitive coding, and routine iteration

This keeps costs down while preserving quality where it actually matters.

In other words: do not spend your smartest model on plumbing unless the plumbing is the hard part.

## Failure modes

Without controls, loops degrade quickly.

Common failure modes:

- retrying the same failure with no new information
- changing many things without observing any of them
- endless coding without running the product
- endless planning without shipping anything
- token burn with no artifact output
- team memory existing only in chat
- verification that is really just the engineer saying "should work"

The fix is always the same:

- shrink scope
- increase observability
- tighten acceptance criteria
- write state to files
- slow the cadence down
- stop when the loop is not learning

## Stop conditions

Every software cell needs stop conditions.

Examples:

- missing credentials
- missing device or emulator
- repeated failure with no new signal
- build system broken at the environment level
- no observable progress after N cycles
- budget cap hit
- user changed direction

Autonomy without stop conditions is just expensive wandering.

## What this is good for

This pattern works well for:

- internal tools
- mobile apps
- web products
- prototypes that need repeated polish
- agent-built software that must actually run
- long-lived side projects
- low-speed continuous product building

It is especially good when you want a product to improve gradually in the background, with real validation, without requiring constant human steering.

## What this is not

This is not:

- a magic startup generator
- a giant autonomous CEO fantasy
- a replacement for product taste
- a substitute for runtime visibility
- a license to skip QA

The human still matters. The human sets direction, taste, and boundaries. The team handles the repetitive execution and validation work in between.

## The human's job

The human should do the things humans are actually good at:

- choose what is worth building
- set taste and product direction
- decide priorities
- evaluate strategic tradeoffs
- step in when the system is stuck or going weird

The team's job is everything else:

- break work down
- implement
- run
- inspect
- log
- refine
- keep moving

## The pattern in one sentence

A software cell is a small LLM team that builds products through repeated, observable, low-speed cycles of planning, implementation, runtime validation, and written state management.

That is the pattern.

Not "AI writes code."

**AI becomes a tiny software team that can see what it built.**
