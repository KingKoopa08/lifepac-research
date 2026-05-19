# AGENTS.md - Homeschool Platform

## Source of truth
Linear is the task source of truth once connected. This repo keeps planning artifacts until Linear import is complete.

## Workflow
- Do not code from vague ideas. Create or update a Linear issue first.
- Every implementation issue needs acceptance criteria.
- Work one issue at a time unless the task is explicitly split.
- Create a branch from the Linear issue when coding begins.
- Open a PR for review before merging.
- Move Linear status as work progresses.

## Curriculum rules
- The LIFEPAC research data is an index/planning foundation.
- Do not add paid workbook content unless Kaecey provides legally usable content or permission.
- Prefer original lesson/activity content built around the outline.
- Keep source and licensing notes with curriculum imports.

## Product rules
- Build parent visibility and student learning together. Do not let one side drift.
- Website/backend comes first so Android has stable APIs.
- Android first, iOS later.
- Keep MVP focused: curriculum import, parent/child accounts, assignments, progress, scores, reporting.

## Verification
Before marking work done, run the smallest meaningful check:
- lint/typecheck/build for code
- importer dry run for data work
- screenshot/manual pass for UI
- API smoke test for backend
