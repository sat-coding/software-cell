# Starter Kit

This document explains how to bootstrap a new project with the software-cell pattern.

## Goal

Spin up a project with:
- operating docs
- task scaffolding
- team personalities
- runtime expectations
- first-cycle instructions

## Minimum setup

Copy these into a project root:
- `templates/VISION.md`
- `templates/ROADMAP.md`
- `templates/BACKLOG.md`
- `templates/CURRENT.md`
- `templates/STATE.md`
- `templates/RUNBOOK.md`
- `templates/QA_LOG.md`
- `templates/DECISIONS.md`
- `templates/TEAM-PERSONALITIES.md`

Optionally add:
- `templates/TASK.md`
- `examples/` as reference

## First 30 minutes

### 1. Define the product
Fill in:
- `VISION.md`
- `ROADMAP.md`

### 2. Define visibility
Fill in `RUNBOOK.md` with:
- how to start the product
- how to test it
- where logs live
- how screenshots or equivalent evidence will be captured

### 3. Choose personalities
Fill in `TEAM-PERSONALITIES.md`

### 4. Create a starter backlog
Put 5-10 small tasks into `BACKLOG.md`

### 5. Start one cycle only
Move exactly one task into active work.
Do not try to automate everything at once.

## Starter project layouts

### Small app
Put files directly in project root:
- app code
- `VISION.md`
- `BACKLOG.md`
- `RUNBOOK.md`
- etc.

### Larger product
Use a dedicated operations directory:
- `product/` for source code
- `ops/` for software-cell files

## Recommended first task

Good first tasks:
- app boots locally
- first screen renders
- health endpoint works
- basic layout exists
- one end-to-end flow runs

Bad first tasks:
- complete product architecture
- fully autonomous background operation
- giant multi-role roadmap execution

## Definition of ready

A project is ready for a software cell when:
- the product has a visible runtime surface
- there is at least one realistic task
- the runbook can explain how to observe the product

## Recommended first checkpoint

After the first cycle, update:
- `CURRENT.md`
- `STATE.md`
- `QA_LOG.md`
- `BACKLOG.md`

This gives the team a real starting memory.
