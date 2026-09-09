# English Practice Engine

A personal English knowledge and practice system for turning trusted learning sources into structured knowledge, active-recall drills, speaking practice, and long-term review.

## Goals

- Convert English-learning books into normalized Knowledge Units (KUs).
- Keep grammar and vocabulary active instead of repeatedly rereading books.
- Train recognition, production, and speaking reflexes.
- Track weak areas and mistakes separately from source knowledge.
- Generate personalized review sessions from structured knowledge.
- Keep copyrighted source files outside Git.

## Architecture

```text
Source books
    ↓
Source metadata + mappings
    ↓
Normalized Knowledge Units
    ↓
Practice generation
    ↓
Review / mistake state
    ↓
Adaptive daily practice
```

The repository is organized around **knowledge concepts, not book chapters**. A book is a source; multiple books may contribute to the same canonical Knowledge Unit.

## Repository structure

```text
english-practice-engine/
├── docs/          # Architecture, migration status, Project instructions
├── sources/       # Source metadata only; no copyrighted PDFs/EPUBs
├── mappings/      # Book unit → canonical knowledge mapping
├── knowledge/     # Normalized grammar/vocabulary KUs + registry index
├── practice/      # Practice-format specifications
├── schemas/       # Machine-readable data contracts
├── prompts/       # Reusable practice prompts
└── user-data/     # Local learning state; real personal state is gitignored
```

## Registered and migrated sources

### Grammar

- **Essential Grammar in Use**, Fourth Edition
- Raymond Murphy
- Cambridge University Press, 2015
- 115 / 115 units mapped
- normalized into canonical grammar KUs, with shared lexical KUs where appropriate

### Vocabulary

- **English Vocabulary in Use: Elementary**, Third Edition
- Michael McCarthy and Felicity O'Dell
- Cambridge University Press, 2017
- A1–A2
- 60 / 60 units mapped
- normalized into 59 vocabulary KUs because Units 40–41 share the canonical `vocabulary.collocation.do-vs-make` KU

The source PDFs remain in the ChatGPT Project source library or another private location and are not committed to this repository.

See `knowledge/index.yaml` and `docs/migration-status.md` for migration coverage.

## Core principles

1. **Source is not knowledge model** — books are references; KUs are canonical concepts.
2. **Normalize before generating practice** — do not make each book unit a permanent domain object.
3. **Active recall first** — review should require retrieval before showing explanations or answers.
4. **Speaking matters** — a topic is not mastered only because it can be recognized.
5. **Track dimensions separately** — recognition, production, and speaking can develop at different speeds.
6. **Track state separately** — knowledge files should stay stable; personal mastery/mistakes should evolve independently.
7. **Do not copy books** — paraphrase explanations and create original examples/exercises.

## Current phase

The initial `normalized-core` migration for both elementary books is complete. The next phase is to make the manual practice and review loop operational: generate sessions from due/weak KUs, evaluate answers, log mistakes locally, and re-test production/speaking weaknesses.

## Roadmap

- [x] v0.1 — Repository scaffold and architecture
- [x] v0.2 — Finalize Knowledge Unit schema
- [x] v0.3 — Map Essential Grammar in Use units to canonical KUs
- [x] v0.4 — Extract and normalize Essential grammar knowledge
- [ ] v0.5 — Define and validate practice generators
- [ ] v0.6 — Add spaced-repetition/review state workflow
- [ ] v0.7 — Add speaking-reflex workflow
- [x] v0.8 — Normalize English Vocabulary in Use: Elementary
- [ ] v1.0 — Daily English Practice Engine
