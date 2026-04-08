# Validation

Validation is the center of the software-cell pattern.

The team is not valuable because it can generate code.
The team is valuable because it can tell whether the code produced a better product.

## Acceptance criteria

Every task should have observable acceptance criteria.

Examples:
- page renders without crash
- button click navigates correctly
- endpoint returns expected success and failure shapes
- no console errors during the tested flow
- screenshot shows improved hierarchy and spacing
- emulator build completes successfully

## Weak vs strong validation

Weak validation:
- should work
- code looks correct
- likely fixed

Strong validation:
- browser snapshot captured
- build command passed
- failing log line disappeared
- API response matches expected shape
- screenshot reviewed by verifier and designer

## Validation layers

### 1. Runtime validation
Did it run at all?

Examples:
- server boots
- app launches
- emulator connects
- health endpoint returns ok

### 2. Functional validation
Did the task behavior work?

Examples:
- flow completes
- button works
- state updates
- API contract matches expectation

### 3. Experience validation
Is the result actually better?

Examples:
- layout clearer
- error state more understandable
- interaction less confusing
- visual hierarchy improved

### 4. State validation
Was the team memory updated?

Examples:
- QA note written
- task marked done or blocked
- decision logged
- next step recorded

## Role split in validation

### Verifier
Should leave:
- pass/fail status
- evidence
- exact repro if failing
- what remains uncertain

### Designer
Should leave:
- concrete visual critique
- exact proposed improvements
- not just adjectives

### Runtime/Ops
Should leave:
- startup steps
- health result
- logs if broken
- recovery notes

## Recommended output format

For each validation pass, record:

- task
- environment used
- command or action performed
- result
- evidence
- open issues
- next recommendation

## Rule of thumb

If another agent or human cannot read the validation notes and understand what actually happened, the validation pass was too vague.
