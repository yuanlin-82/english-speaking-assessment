# Fluency (owned evidence chain)

## Why not “take the vendor fluency number”?

In this product line, **vendor fluency scores correlated poorly with expert fluency ratings** relative to what the report needed. Pronunciation-accuracy and content-completeness-style scores from the vendor remained usable as **inputs to composition**; fluency did not—so fluency became an **in-house** construct with its own observables and validation story.

Public claim: **own the fluency evidence chain**; treat vendor fluency (if present) as non-authoritative for the report until proven otherwise.

A concrete field probe (same text, deliberately broken delivery, scores still stuck high) is in [failure-case-vendor-fluency-insensitive.md](failure-case-vendor-fluency-insensitive.md).

---

## Evidence shape (utterance → perceived)

Without publishing formulas or thresholds:

| Family | Examples of observables | Role |
| --- | --- | --- |
| **Rate** | Speaking rate / articulation rate style metrics | Tempo of delivery |
| **Pause** | Silent / filled pause patterns, placement | Breakdown vs planning |
| **Repair** | Self-corrections, repetitions, restarts; filler inventory | Effort / planning load |
| **Aggregation** | Map utterance features → a score that tracks **perceived fluency** (expert ear), not a vendor summary float | Report dimension |

**Design stance:** extract **interpretable utterance features**, then **predict perceived fluency**. That path is treated as reasonable for hiring oral reports: it stays falsifiable (features must move when delivery moves) and alignable to human ratings.

**Model choice (public shape only):** several mapping algorithms were tried in-house; **regression** performed as well as or better than the alternatives we compared for this use. The important claim is the **feature → perceived-fluency** target, not a branded model family. Exact coefficients and training sets stay private.

**Repair in the fitted model:** repair/hesitation features are still extracted (and still suffer when ASR drops false starts or fillers), but in the regression they were **weak / non-salient** (very small coefficients). So ASR damage to repair is acknowledged, yet it was **not treated as a blocking defect** for the report fluency axis—rate and pause families carried more of the predictive work. Exact weights stay private.

**Validation shape:** alignment to perceived fluency followed a **standard hold-out discipline** (separate train vs validation/test material)—not a single pass fitted and scored on the same clips. Metrics and splits stay private; the public claim is that the mapping was checked out-of-sample, not only eyeballed.

**Repair / hesitation identification** may use an LLM (or similar classifier) over transcripts or token streams as a **feature extractor**, not as the sole fluency judge. Temporal features still need audio timing (ASR timestamps or equivalent).

This stance is in the same broad family as classic automated speaking work that builds fluency-related features from ASR and maps them to human scores (for example early SpeechRater-style pipelines)—with the same caveat those papers stress: automatic scores are only as good as ASR + feature design + human alignment, and early systems were often scoped to lower-stakes use until coverage improved.

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
- Cross-accent / channel noise → ASR error propagates into repair false positives; mitigated in practice because repair contributed little in the regression we ship against.
