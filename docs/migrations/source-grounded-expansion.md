# Source-grounded expansion flow

The initial migration created 153 canonical Knowledge Units at `normalized-core` status. This phase expands those KUs from the two registered source books without turning the repository into a copy of either book.

## Status model

```text
normalized-core -> expanded -> curated
```

- `normalized-core`: canonical ID, source mapping, core concept, and practice hooks exist.
- `expanded`: the important distinctions taught by the referenced source units are represented in reusable form: forms/usage/contrasts/common mistakes for grammar; key items/collocations/confusions/pronunciation notes where relevant for vocabulary. Examples and drills are original.
- `curated`: the expanded KU has been exercised with the learner and refined using observed production/speaking mistakes.

## Migration rules

1. Read the referenced source unit(s) before changing a KU.
2. Preserve canonical IDs and existing source mappings unless the source clearly requires a mapping correction.
3. Store the reusable concept, not the page layout or exercise set.
4. Paraphrase source explanations. Do not copy long passages, exercise sets, answer keys, or pages.
5. Distinguish source-derived knowledge from original practice material. Original examples/drills may use everyday and software-engineering contexts.
6. Prefer one retrieval trigger per KU. Split only when a concept needs materially different review behavior.
7. For vocabulary, prioritize useful chunks and collocations rather than isolated word lists. Preserve source-highlighted common mistakes and confusions.
8. A batch is complete only when its KUs have `status: expanded` and the runner state is updated.

## Batch order

The migration proceeds in source order for traceability, while writing into canonical KUs:

- Grammar: Essential Grammar in Use Units 1-115.
- Vocabulary: English Vocabulary in Use: Elementary Units 1-60.

Cross-book KUs are expanded once and keep all relevant `source_refs`.

## Completion criteria

The source-grounded expansion phase is complete when all 153 canonical KUs are `expanded`, all mapped source units remain covered, and `knowledge/index.yaml` reports zero remaining `normalized-core` KUs.
