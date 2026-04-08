# Runtime Surfaces

A software cell needs runtime visibility.

If the team cannot observe the running product, it cannot improve it reliably.

## Core question

Every project should answer this explicitly:

**How will the team observe whether the product actually works?**

Put the answer in `RUNBOOK.md`.

## Common runtime surfaces

### Web app
- local dev server
- browser snapshots
- console logs
- screenshots
- network responses

### Mobile app
- emulator or physical device
- build output
- screenshots
- runtime logs
- crash traces

### Backend/API
- health endpoints
- curl/API responses
- test runs
- logs
- metrics if available

### CLI/tooling project
- command output
- exit codes
- fixture inputs/outputs
- regression tests

## Good runtime visibility

Good visibility means the team can answer:
- did it start?
- what does it look like?
- what failed?
- where is the evidence?

## Bad runtime visibility

Bad visibility looks like:
- only reading code
- only reasoning from diffs
- no screenshots
- no logs
- no test execution
- no way to inspect the running product

## Project requirement

Before starting meaningful work, define:
- startup command
- validation command(s)
- log source
- visual inspection path if UI exists
- recovery path if startup fails

## Example runtime checklist for a mobile app

- install dependencies
- boot emulator
- run app
- confirm first screen renders
- capture screenshot
- record any crashes
- test one core flow
- write result to `QA_LOG.md`

## Example runtime checklist for a web app

- start dev server
- open browser
- capture home screen snapshot
- test one core flow
- inspect console/network
- log result in `QA_LOG.md`
