# Practice

Practice content is generated from Knowledge Units rather than copied from book exercises.

## Practice modes

- recognition
- controlled production
- Vietnamese → English
- personal production
- speaking reflex
- mixed grammar/vocabulary
- error-targeted retest

## Manual workflow

The first operational version is intentionally simple and application-free.

Use:

- `docs/manual-practice-workflow.md` for session selection, feedback, mastery updates, review intervals, and retests
- `schemas/practice-session.schema.json` for a structured session/result shape
- `practice/example-session.yaml` as a human-readable example
- `prompts/daily-review.md` to build a session
- `prompts/evaluate-answer.md` to evaluate one answer
- `schemas/review-state.schema.json` for private per-KU learning state

## Core rule

Ask first, then evaluate. Do not reveal the target rule before retrieval unless the learner explicitly asks to study it first.

Real generated sessions do not need to be committed. A future application may materialize sessions/results as JSON or YAML, but the repository should first validate the manual learning loop.
