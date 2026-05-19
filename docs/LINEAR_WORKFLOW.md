# Linear Workflow

## Purpose
Use Linear the way Alex describes in the video: the AI plans the work up front, creates issues with acceptance criteria, then works issue by issue while Linear tracks priority and progress.

## Setup checklist

1. Create Linear workspace or team for the homeschool project.
2. Create one project: Homeschool Platform MVP.
3. Connect GitHub to Linear.
4. Create labels:
   - area:curriculum
   - area:web
   - area:android
   - area:parent
   - area:student
   - area:backend
   - area:admin
   - area:qa
   - type:feature
   - type:bug
   - type:research
   - type:task
   - blocked
5. Import `planning/linear-backlog.csv` into Linear.
6. Connect issues to GitHub branches and PRs as implementation starts.

## Agent operating rules

- Linear is the source of truth for tasks.
- Work only one implementation issue at a time unless a task is explicitly split across agents.
- Every issue must have acceptance criteria before coding starts.
- Every code issue gets a branch named from the Linear issue key.
- Move issue to In Progress when work starts.
- Move issue to In Review when a PR or testable artifact exists.
- Move issue to Done only after verification passes.
- If blocked, write the blocker plainly in the issue and set status to Blocked.

## Issue template

### Problem
What user or system problem are we solving?

### Scope
What is included?

### Out of scope
What should not be built in this issue?

### Acceptance criteria
- Given/when/then or checklist format

### Verification
- Test, lint, build, screenshot, or manual review step

## Priority rules

P0: Blocks the platform from existing or blocks all downstream work.
P1: Required for MVP.
P2: Important but can wait until MVP core works.
P3: Later polish or expansion.

## Suggested first execution order

1. HOM-001 through HOM-006: Linear and repo foundation.
2. HOM-010 through HOM-017: curriculum data model and importer.
3. HOM-020 through HOM-029: web/backend MVP.
4. HOM-030 through HOM-039: parent portal.
5. HOM-040 through HOM-049: student experience.
6. HOM-060 through HOM-069: Android MVP.
7. HOM-080 through HOM-089: beta readiness.
