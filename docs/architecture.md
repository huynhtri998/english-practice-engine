# Architecture

## 1. Source layer

The source layer records source metadata and references. Copyrighted PDFs/EPUBs stay outside Git.

```text
sources/
├── essential-grammar-in-use-4e.yaml
└── english-vocabulary-in-use-elementary-3e.yaml
```

Books are authorities and syllabus inputs, not the canonical domain model.

## 2. Mapping layer

Mappings connect every source unit to one or more canonical Knowledge Unit (KU) IDs.

```text
source unit → canonical KU ID(s)
```

A mapping can be many-to-one when several source units teach one reusable concept. Different books may also contribute to the same KU.

## 3. Knowledge layer

Canonical KUs are stored as schema-valid YAML and organized by concept/category, not by book.

```text
knowledge/
├── index.yaml
├── grammar/
│   ├── present/
│   ├── past/
│   ├── questions/
│   └── ...
└── vocabulary/
    ├── people/
    ├── home/
    ├── core-verbs/
    └── ...
```

`schemas/knowledge-unit.schema.json` is the contract. Each KU stores normalized, paraphrased core knowledge and source references. It does **not** copy book pages or exercise sets.

`status: normalized-core` means the source units are covered and the reusable core has been migrated, while the original source remains available in the ChatGPT Project for deeper lookup.

## 4. Practice layer

Practice is generated from KUs, not copied from source exercises.

Preferred modes:

1. Recognition
2. Controlled production
3. Vietnamese → English
4. Personal production
5. Speaking reflex
6. Mixed review
7. Error-targeted re-test

## 5. User-state layer

Stable knowledge and personal review state are separate. Track at least:

- recognition mastery
- production mastery
- speaking mastery
- last / next review
- interval
- error categories

Real personal state is gitignored because the repository may be public.

## 6. Review policy

Default review sequence:

```text
1 → 3 → 7 → 14 → 30 → 60 days
```

Production and speaking errors should shorten the next interval more aggressively than recognition-only errors.

## 7. Migration policy

For copyrighted books:

- register source metadata
- map every source unit
- normalize concepts into KUs
- paraphrase explanations
- keep original examples/exercises out of Git
- create original practice prompts
- retain source references for traceability

## 8. Repository evolution

Keep the current phase data-first: YAML + JSON Schema + Markdown documentation. Build an application only after the knowledge model and manual practice loop are useful.
