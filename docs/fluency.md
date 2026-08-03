# Fluency (owned evidence chain)

## Why not “take the vendor fluency number”?

In this product line, **vendor fluency scores correlated poorly with expert fluency ratings** relative to what the report needed. Accuracy / integrity-style scores from the vendor remained usable as **inputs to composition**; fluency did not—so fluency became an **in-house** construct with its own observables and validation story.

Public claim: **own the fluency evidence chain**; treat vendor fluency (if present) as non-authoritative for the report.

---

## Evidence shape (utterance → perceived)

Without publishing formulas or thresholds:

| Family | Examples of observables | Role |
| --- | --- | --- |
| **Rate** | Speaking rate / articulation rate style metrics | Tempo of delivery |
| **Pause** | Silent / filled pause patterns, placement | Breakdown vs planning |
| **Repair** | Self-corrections, repetitions, restarts; filler inventory | Effort / planning load |
| **Aggregation** | Combine utterance features → score aligned to **perceived fluency** | Report dimension |

**Repair / hesitation identification** may use an LLM (or similar classifier) over transcripts or token streams as a **feature extractor**, not as the sole fluency judge. Temporal features still need audio timing (ASR timestamps or equivalent).

Validation stance (research / product QA): multiple regression or similar mapping from utterance features → expert perceived fluency—**methods published elsewhere or kept private**; this repo only states the chain.

---

## Separation of concerns

| Component | Responsibility |
| --- | --- |
| ASR + timing | Provide words and time alignment |
| Lexicon / syllable helpers | Support rate-related features (see [lexicon-layer.md](lexicon-layer.md)) |
| Repair / filler tagging | Label disfluency phenomena |
| Fluency scorer | Map features → report fluency |
| Expert panel / QA | Anchor and audit |

Do not collapse “LLM said fluent” into the fluency score without the temporal / pause / repair backbone.

---

## Limits

- Short answers → unstable rate/pause estimates; need minimum-duration or confidence flags.
- Read-aloud vs free expression → different expected pause/repair profiles; type-aware interpretation helps.
- Cross-accent / channel noise → ASR error propagates into repair false positives.
