# User Data

This folder documents the shape of personal learning state.

Real learner state must stay private and is gitignored by default.

Suggested local files:

- `progress.yaml` — per-KU mastery and review timing
- `mistakes.yaml` — reusable error history/categories
- `review-queue.yaml` — due and weak KUs selected for upcoming review
- `private/` — any additional personal session data

Use `example-progress.yaml` as a tracked example only.

## Skill dimensions

Keep these separate:

- recognition
- production
- speaking

A learner may recognize a structure while still failing to produce it automatically.

## Review cadence

Default interval progression:

`1 → 3 → 7 → 14 → 30 → 60 days`

Production and speaking errors should normally schedule earlier review than recognition-only errors.

The operational rules live in `docs/manual-practice-workflow.md`; the data contract lives in `schemas/review-state.schema.json`.
