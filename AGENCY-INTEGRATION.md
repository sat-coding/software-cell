# Agency Agents Integration

This document maps the `agency-agents` personality library into the software-cell pattern.

Upstream reference:
- https://github.com/msitarzewski/agency-agents

The goal is **not** to import hundreds of agents blindly.
The goal is to use that repository as a **personality and role source** for a smaller persistent software team.

## Principle

A software cell only needs a few stable roles.
Agency Agents gives those roles sharper voice, behavior, standards, and domain posture.

So instead of creating generic workers like:
- engineer
- designer
- verifier
- coordinator

we can instantiate them with stronger personalities from Agency Agents.

## Recommended core mapping

### 1. Coordinator

Primary upstream candidates:
- `product/product-manager.md`
- `project-management/project-management-project-shepherd.md`
- `project-management/project-management-studio-producer.md`

Use when:
- selecting next task
- setting acceptance criteria
- sequencing work
- preventing chaos
- deciding whether to keep iterating or pause

Behavior we want:
- calm
- scope-aware
- anti-chaos
- artifact-oriented
- does not code unless necessary

### 2. Engineer

Primary upstream candidates:
- `engineering/engineering-senior-developer.md`
- `engineering/engineering-software-architect.md`
- `engineering/engineering-rapid-prototyper.md`
- `engineering/engineering-frontend-developer.md`
- `engineering/engineering-mobile-app-builder.md`
- `engineering/engineering-backend-architect.md`

Use when:
- implementing features
- fixing bugs
- refactoring
- building MVP slices

Behavior we want:
- writes code fast but not sloppy
- leaves runnable output
- documents what changed
- respects acceptance criteria

### 3. Verifier / QA

Primary upstream candidates:
- `testing/testing-reality-checker.md`
- `testing/testing-evidence-collector.md`
- `testing/testing-api-tester.md`
- `testing/testing-test-results-analyzer.md`

Use when:
- checking if the thing actually works
- collecting screenshots/logs/test evidence
- validating acceptance criteria
- writing QA notes

Behavior we want:
- skeptical
- evidence-first
- does not accept "should work"
- always leaves observable artifacts

### 4. Designer

Primary upstream candidates:
- `design/design-ui-designer.md`
- `design/design-ux-architect.md`
- `design/design-brand-guardian.md`
- `design/design-visual-storyteller.md`
- `design/design-whimsy-injector.md`

Use when:
- reviewing UI screenshots
- improving layout/hierarchy/polish
- checking consistency and interaction quality

Behavior we want:
- sharp taste
- concrete critique
- visual clarity over vague adjectives
- able to suggest exact UI changes

### 5. Runtime / Ops

Primary upstream candidates:
- `engineering/engineering-devops-automator.md`
- `engineering/engineering-sre.md`
- `engineering/engineering-incident-response-commander.md`

Use when:
- starting services
- collecting logs
- recovering failed processes
- defining runbooks
- checking health and runtime state

Behavior we want:
- reliability-first
- minimal drama
- fast diagnosis
- writes down recovery steps

## Operating rule

Each active role in the software cell should have:
- a **function**
- a **personality source**
- a **required artifact output**

Example:
- Function: verifier
- Personality source: `testing/testing-reality-checker.md`
- Required artifact output: screenshot + pass/fail note + exact bug repro if failed

## Personality usage pattern

Do not treat personality as cosplay.
It should change:
- what the agent notices
- how strict it is
- what artifacts it leaves behind
- what it considers "done"

Good personality use:
- a verifier becomes harder to fool
- a designer becomes more concrete and visually opinionated
- a coordinator becomes better at scope control
- an engineer becomes more consistent in implementation style

Bad personality use:
- just changing tone or emojis
- making agents more verbose without improving output quality

## Suggested software-cell presets

### Preset A — MVP Build Cell

- Coordinator -> `product/product-manager.md`
- Engineer -> `engineering/engineering-rapid-prototyper.md`
- Verifier -> `testing/testing-reality-checker.md`
- Designer -> `design/design-ui-designer.md`
- Runtime -> `engineering/engineering-devops-automator.md`

Best for:
- shipping fast
- rough MVPs
- proving product ideas

### Preset B — Product Polish Cell

- Coordinator -> `project-management/project-management-project-shepherd.md`
- Engineer -> `engineering/engineering-senior-developer.md`
- Verifier -> `testing/testing-evidence-collector.md`
- Designer -> `design/design-ux-architect.md`
- Runtime -> `engineering/engineering-sre.md`

Best for:
- refining existing apps
- debugging user-facing quality issues
- iterative UX improvement

### Preset C — Mobile App Cell

- Coordinator -> `product/product-manager.md`
- Engineer -> `engineering/engineering-mobile-app-builder.md`
- Verifier -> `testing/testing-reality-checker.md`
- Designer -> `design/design-ui-designer.md`
- Runtime -> `engineering/engineering-devops-automator.md`

Best for:
- React Native / native mobile work
- emulator/device run loops
- screenshot-driven iteration

## Integration into the software-cell pattern

The clean integration is:

1. Keep the software-cell structure as the operating system
2. Use Agency Agents as the personality/role library
3. Assign one upstream profile to each active role
4. Record the chosen mapping in a local file
5. Keep the team small and persistent

In other words:
- software-cell = process
- agency-agents = personalities

## Minimal local file to add per project

Create a file like `TEAM-PERSONALITIES.md`:

```md
# Team Personalities

- Coordinator: product/product-manager.md
- Engineer: engineering/engineering-rapid-prototyper.md
- Verifier: testing/testing-reality-checker.md
- Designer: design/design-ui-designer.md
- Runtime: engineering/engineering-devops-automator.md
```

This makes the team identity explicit and stable across sessions.

## Recommendation

Do not integrate the whole Agency repo.
Start with one of the presets above and use only 4-5 roles.

The goal is not maximum variety.
The goal is a compact software team with stronger judgment and clearer output behavior.
