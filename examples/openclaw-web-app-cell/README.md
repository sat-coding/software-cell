# OpenClaw Web App Cell Example

This example shows a small software cell for a web app running in OpenClaw.

## Roles

- Coordinator -> main session
- Engineer -> spawned coding worker
- Verifier -> worker using browser + logs
- Designer -> screenshot reviewer
- Runtime -> process / health checker

## Core artifacts

- browser snapshot
- console/log output
- QA note
- updated current cycle state

## Example cycle

1. Select one UI task
2. Engineer implements
3. Runtime starts server
4. Verifier checks in browser
5. Designer comments on screenshot
6. Coordinator decides next move
