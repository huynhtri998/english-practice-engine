# Knowledge

Canonical project knowledge lives here.

## Storage format

Knowledge Units are YAML objects validated against:

```text
schemas/knowledge-unit.schema.json
```

Use concept-oriented paths, for example:

```text
knowledge/grammar/present/present-simple.yaml
knowledge/grammar/present/present-simple-vs-continuous.yaml
knowledge/vocabulary/people/family.yaml
knowledge/vocabulary/core-verbs/get.yaml
```

The file path is for navigation. The stable identity is the `id` field.

## Rules

- Organize by reusable concept, not by book chapter.
- Multiple source units/books may contribute to one KU.
- Keep source references in `source_refs`.
- Paraphrase explanations; do not copy pages or exercise sets.
- Use `status: normalized-core` for first-pass migration.
- Create original examples and practice prompts.
- Keep user mastery/review state outside these files.

`knowledge/index.yaml` is the catalog used to discover all canonical KUs.
