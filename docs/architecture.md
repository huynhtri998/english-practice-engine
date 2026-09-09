# Architecture

## 1. Source layer

The source layer describes where knowledge came from. It contains metadata and references, not copied book content.

```text
sources/
├── essential-grammar-in-use-4e.yaml
└── english-vocabulary-in-use-elementary-3e.yaml
```

A source is an authority/reference, not the domain model.

## 2. Mapping layer

Mappings connect source units to canonical Knowledge Units.

```text
Book unit → one or more canonical KU IDs
```

This allows several books to enrich the same concept later without duplicating knowledge by title or edition.

## 3. Knowledge layer

Knowledge is organized by concept, for example:

```text
knowledge/grammar/present/present-simple.md
knowledge/grammar/present/present-continuous.md
knowledge/grammar/present/present-simple-vs-continuous.md
knowledge/vocabulary/work/jobs.md
knowledge/vocabulary/collocations/do-vs-make.md
```

A KU should be paraphrased and source-referenced. Grammar KUs typically include a mental model, form, usage, contrasts, common mistakes, original examples, and practice hooks. Vocabulary KUs can additionally emphasize meanings, collocations, confusions, and production contexts.

## 4. Practice layer

Practice is generated from KUs instead of copied from source exercises.

Preferred practice modes:

1. Recognition — identify the grammar/meaning.
2. Controlled production — transform or complete a sentence.
3. Vietnamese → English production.
4. Personal production — answer about real life/work.
5. Speaking reflex — answer within roughly 2–3 seconds.
6. Mixed review — choose the right grammar/vocabulary without being told the topic.

## 5. User-state layer

Personal learning state is separate from stable knowledge.

Track at least:

- recognition mastery
- production mastery
- speaking mastery
- last review
- next review
- current interval
- error categories

Real user state is gitignored by default because this repository may be public.

## 6. Review policy

Default review intervals can start with:

```text
1 → 3 → 7 → 14 → 30 → 60 days
```

Intervals should shrink when production/speaking is weak and grow after successful retrieval. Do not reread the explanation before testing recall.

## 7. Repository evolution

Start with Markdown + YAML + JSON Schema. Avoid building a web stack until the knowledge model and practice loop are useful manually.

Suggested phases:

```text
v0.x: grammar content architecture
v0.x: manual practice protocol
v0.x: review state
v0.x: vocabulary normalization
v1.0: daily practice loop
v2.x: CLI/API/web app only if needed
```
