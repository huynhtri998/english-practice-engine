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
├── docs/          # Architecture and ChatGPT Project instructions
├── sources/       # Source metadata only; no copyrighted PDFs/EPUBs
├── mappings/      # Book unit → canonical knowledge mapping
├── knowledge/     # Normalized grammar/vocabulary knowledge
├── practice/      # Practice-format specifications
├── schemas/       # Machine-readable data contracts
├── prompts/       # Reusable practice prompts
└── user-data/     # Local learning state; real personal state is gitignored
```

## Registered sources

### Grammar

- **Essential Grammar in Use**, Fourth Edition
- Raymond Murphy
- Cambridge University Press, 2015
- Elementary grammar reference and practice book
- 115 units

### Vocabulary

- **English Vocabulary in Use: Elementary**, Third Edition
- Michael McCarthy and Felicity O'Dell
- Cambridge University Press, 2017
- A1–A2 vocabulary reference and practice book
- 60 units

The source PDFs should remain in the ChatGPT Project source library or another private local location and must not be committed to this repository.

## Core principles

1. **Source is not knowledge model** — books are references; KUs are canonical concepts.
2. **Normalize before generating practice** — do not make each book unit a permanent domain object.
3. **Active recall first** — review should require retrieval before showing explanations or answers.
4. **Speaking matters** — a topic is not mastered only because it can be recognized.
5. **Track dimensions separately** — recognition, production, and speaking can develop at different speeds.
6. **Track state separately** — knowledge files should stay stable; personal mastery/mistakes should evolve independently.
7. **Do not copy books** — paraphrase explanations and create original examples/exercises.

## Current phase

Grammar normalization comes first. Vocabulary source metadata is registered now, but detailed vocabulary normalization can follow after the grammar KU taxonomy and manual review loop are stable.

## Roadmap

- [x] v0.1 — Repository scaffold and architecture
- [ ] v0.2 — Finalize Knowledge Unit schema
- [ ] v0.3 — Map Essential Grammar in Use units to canonical KUs
- [ ] v0.4 — Extract and normalize Essential grammar knowledge
- [ ] v0.5 — Define practice generators
- [ ] v0.6 — Add spaced-repetition/review state
- [ ] v0.7 — Add speaking-reflex workflow
- [ ] v0.8 — Normalize English Vocabulary in Use: Elementary
- [ ] v1.0 — Daily English Practice Engine
