# Lexicon / morphology layer (shape only)

Fluency and related features sometimes need **word-level helpers**: syllable estimates, lemma / morphology normalization, filler lists.

## Public shape

| Piece | Role | Public constraint |
| --- | --- | --- |
| Core word list | Coverage for common oral vocabulary | Built from licensed / allowed sources in production; **no copyrighted dump in this repo** |
| Phonetic → syllable heuristics | Support rate-style features | Method sketch only |
| Morphology / inflection handling | Normalize surface forms for lookup | May use LLM-assisted tagging in pipelines; prompts omitted |
| Filler / discourse-marker list | Feed repair / hesitation features | Inventory is product data; examples only if non-sensitive |

## What not to publish

- Scraped or redistributed dictionary text
- Full production word tables
- Exact syllable rules that reverse-engineer a licensed resource

This layer is **supporting infrastructure** for fluency features—not a standalone “vocabulary score” product claim.
