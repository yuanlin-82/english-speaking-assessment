# English speaking assessment (methodology)

Public notes on **how oral English is measured and composed into scores** in interview / talent products—not a scoring API, not a model card.

Companion repo (dialogue **routing**, not ability scores):

- [ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map)

---

## What this is

| Layer | Public claim |
| --- | --- |
| **Task design** | Interview-oriented speaking tasks designed under an evidence-centered framing (what each item elicits). |
| **Fluency** | A self-built evidence chain (rate / pause / repair → perceived fluency), motivated by weak alignment of vendor “fluency” with expert ratings. |
| **Accuracy & integrity** | Treated as **vendor-provided score types**; this repo documents **how they are composed** into reports—not how the vendor measures them internally. |
| **Composition** | Brief vs detailed report contracts: which item types enter, how dimensions weight, how missing items affect totals—**shape only**, no production tables. |

Honest boundary: CAF (complexity–accuracy–fluency) is theoretically cleaner. Product **integrity** is an operational construct (task completion / content adequacy), not linguistic complexity.

---

## Reading order

1. [docs/construct.md](docs/construct.md) — constructs, CAF vs product dimensions  
2. [docs/task-design.md](docs/task-design.md) — five item types and what they evidence  
3. [docs/fluency.md](docs/fluency.md) — why fluency is owned in-house; observable chain  
4. [docs/score-composition.md](docs/score-composition.md) — vendor scores + report composition contract  
5. [docs/lexicon-layer.md](docs/lexicon-layer.md) — supporting lexicon / morphology layer (shape only)  
6. [docs/limits.md](docs/limits.md) — what this repo will not claim  

---

## What is deliberately omitted

See [NOTICE.md](NOTICE.md). Especially: production weights, IELTS mapping as a product claim, dictionary dumps, audio, and vendor internals.

---

## Author

Applied psychology (assessment) background; content / assessment design on AI interview products.  
GitHub: [yuanlin-82](https://github.com/yuanlin-82)
