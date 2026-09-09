# Knowledge Migration Status

## Sources

| Source | Units mapped | Canonical contribution |
| --- | ---: | ---: |
| Essential Grammar in Use, 4e | 115 / 115 | 99 KU targets |
| English Vocabulary in Use: Elementary, 3e | 60 / 60 | 59 KU targets |

After cross-book merging, the repository contains **153 canonical Knowledge Units**:

- 94 grammar KUs
- 59 vocabulary KUs

## Meaning of `normalized-core`

The initial migration is intentionally a normalized core, not a copy of the books.

Each KU:

- points back to source unit numbers
- stores the reusable concept or lexical inventory needed for retrieval
- uses paraphrased explanations
- includes original practice-generation hooks
- avoids copying source exercise sets, answer keys, or long passages

The source PDFs in the ChatGPT Project remain the detailed reference for deeper explanations, pronunciation detail, illustrations, and source exercises.

## Cross-book merges

The first migration already merges overlapping material into shared KUs:

- `vocabulary.verb.go`
- `vocabulary.verb.get`
- `vocabulary.verb.have`
- `vocabulary.collocation.do-vs-make`
- `vocabulary.phrasal-verbs-basic`

This is intentional: books are sources; KUs are the canonical knowledge model.
