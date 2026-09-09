# Manual Practice Workflow

This phase turns the expanded Knowledge Units into repeatable daily practice without building an application yet.

## Goal

Optimize retrieval and speaking reflex, not rereading.

The loop is:

```text
review state
    ↓
select due + weak KUs
    ↓
generate retrieval-first session
    ↓
learner answers
    ↓
evaluate by skill dimension
    ↓
log mistakes + update mastery
    ↓
schedule targeted retest + next review
```

## Session selection

Select KUs in this priority order:

1. overdue KUs (`next_review <= today`)
2. repeated production/speaking mistakes
3. low speaking mastery
4. low production mastery
5. low recognition mastery
6. maintenance items due today

Avoid selecting only one grammar family unless the learner asks for focused practice. Mixed sessions should include competing structures when possible.

## Default session

A normal 20–30 minute session uses approximately:

- 5 grammar retrieval items
- 5 Vietnamese → English items
- 5 mixed grammar/vocabulary items
- 5 speaking-reflex questions
- targeted re-tests for mistakes made earlier in the same session

Counts are guidelines, not quotas.

## Retrieval-first rule

Do not show the rule before the learner answers unless the learner explicitly asks to study/explain first.

For each item:

1. ask one prompt
2. wait for the answer
3. evaluate correctness and naturalness
4. if wrong, give the corrected sentence
5. explain the smallest useful rule/contrast
6. classify the error
7. queue a different retest later in the same session when useful

## Skill dimensions

Track these separately:

- `recognition` — understands/selects the correct form or meaning
- `production` — can build the sentence from a prompt
- `speaking` — can answer naturally with low latency

Recognition success must not automatically increase production or speaking mastery.

## Error categories

Prefer stable, reusable categories such as:

- tense-selection
- verb-form
- auxiliary
- agreement
- word-order
- article
- determiner
- preposition
- pronoun
- countability
- collocation
- vocabulary-choice
- unnatural-phrasing

A recurring category should trigger an earlier review than a one-off recognition error.

## Review intervals

Default progression:

```text
1 → 3 → 7 → 14 → 30 → 60 days
```

Adjustment rules:

- strong across all dimensions → advance one interval step
- recognition correct but production weak → keep or shorten interval
- speaking hesitation/error → schedule earlier than recognition-only weakness
- repeated production/speaking error → retest in-session and use the next short interval
- major confusion between two KUs → create contrast practice before advancing

## Suggested mastery updates

Do not treat these as mathematically precise scores. They are practical estimates.

For one item targeting a dimension:

- strong, natural answer: `+0.05`
- correct after hesitation/minor repair: `+0.02`
- wrong but self-corrected: no change or `-0.01`
- wrong after feedback: `-0.03`
- repeated same error: `-0.05`

Clamp each dimension to `0.0–1.0`.

## Same-session retest

When a useful error occurs, create a different item that tests the same distinction later in the session.

Example:

```text
error: I am work from home today.
category: verb-form
KU: grammar.present-continuous

later retest:
What are you working on this week?
```

Do not repeat the exact sentence.

## Daily command protocol

When the learner says `học hôm nay`, `review hôm nay`, or `practice`:

1. inspect available review state if present
2. choose due/weak KUs
3. if no real state exists yet, seed the session from foundational and contrast-heavy KUs
4. ask one item at a time
5. maintain temporary session errors in the conversation
6. update persistent state only when the workflow has an authorized/private place to store it

## Privacy

Real learner progress, mistakes, and review queues stay outside tracked Git files. The repository only stores schemas, examples, rules, and templates.
