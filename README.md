# English speaking assessment (methodology)

## 中文导读（约1分钟）

本仓库记录招聘 / 人才场景里 **任务型英语口语如何测量、如何组成报告分**——不是评分 API，也不是模型卡。

- **主线**：固定/半固定口语任务 → 发音、流利度、内容完整度等 → 报告合成。  
- **务必分开**：任务口语能力分 ≠ 交互式口语定级 ≠ **用英语做的胜任力面试**（后者收岗位证据，见 [decision-map](https://github.com/yuanlin-82/ai-interview-decision-map)）。  
- **五分钟入口**：[task-vs-interaction.md](docs/task-vs-interaction.md)（形态 vs 构念、demand 条、多角度挖证据 vs 需求带定标）。

生产权重与厂商内部实现不公开；此处只写可分享的方法论与边界。

---

Public notes on **how oral English is measured and composed into scores** in interview / talent products—not a scoring API, not a model card.

**Author role:** content / assessment design—report **constructs**, task design, fluency ownership when vendors fail, composition shape. Not a claim to own speech-vendor internals or a full CEFR instrument.

Companion (dialogue **routing**, not ability scores): [ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map). Production scoring configs stay private; this repo is methodology only.

Whole-session product context (oral as one weighted report dimension): [system map on profile](https://github.com/yuanlin-82/yuanlin-82/blob/main/docs/system-map.md).

---

## 5-minute visitor guide

| Read first | Product problem it answers |
| --- | --- |
| [docs/task-vs-interaction.md](docs/task-vs-interaction.md) | Task vs interaction vs competency-in-English; demand bar; same LLM / different evidence gaps (multi-angle vs demand band) |
| [docs/notes-working-metaphor.md](docs/notes-working-metaphor.md) | Optional intuition only—not a measurement claim |
| [docs/fluency.md](docs/fluency.md) + [failure-case-vendor-fluency-insensitive.md](docs/failure-case-vendor-fluency-insensitive.md) | Why “fluency API” was not enough; in-house rate / pause / repair |
| [docs/content-completeness.md](docs/content-completeness.md) | Coverage under automation limits—not examiner depth |

Then: [construct.md](docs/construct.md) · [score-composition.md](docs/score-composition.md) · [limits.md](docs/limits.md).

---

## How to use these scores (stakeholder)

1. **Task-based oral scores** answer: under standard speaking tasks, how is pronunciation accuracy, fluency, and content completeness?  
2. **English-medium competency interviews** answer: using English as the channel, what job evidence do we get? — see the decision-map repo; do not read follow-up quality as an oral band.  
3. **Do not merge them:** movie-like speech ≠ hire signal; fluent emptiness ≠ strong competency; unanswered items **lower** the oral composite; the report does not separately label incompleteness ([missing-responses.md](docs/missing-responses.md)).

---

## What this is

**Main spine:** speaking evidence is elicited in a **task-based** or **interaction-based** family (exam brands are examples only, not category names). Neither is universally superior; this repo documents a **task-based** hiring oral path. See [docs/task-vs-interaction.md](docs/task-vs-interaction.md).

| Layer | Public claim |
| --- | --- |
| **Elicitation family** | Task-based vs interaction-based; plus a hard separation from **English-medium competency interviews**. |
| **Task design** | Interview-oriented speaking tasks under an evidence-centered framing (what each item elicits). |
| **Fluency** | A self-built evidence chain (rate / pause / repair → perceived fluency) when vendor “fluency” fails expert alignment. |
| **Pronunciation accuracy & content completeness** | Often **vendor-provided** score types plus composition here. Content completeness = task coverage (automation compromise), ≠ CAF complexity / examiner depth. |
| **Composition** | Brief vs detailed report contracts; missingness rules—**shape only**, no production tables. |

---

## Reading order

1. [docs/task-vs-interaction.md](docs/task-vs-interaction.md) — elicitation families; interactive oral bar; HR “looks like exam” / task vs free-chat frictions  
2. [docs/construct.md](docs/construct.md) — report constructs, CAF vs product dimensions  
3. [docs/task-design.md](docs/task-design.md) — five item types and what they evidence  
4. [docs/stimulus-selection.md](docs/stimulus-selection.md) — scene filter, format-controlled difficulty, TTS / sampling honesty  
5. [docs/stimulus-packaging.md](docs/stimulus-packaging.md) — still + audio muxed as one “video” attachment  
6. [docs/content-completeness.md](docs/content-completeness.md) — coverage axis as automation compromise; why answer freedom is bounded  
7. [docs/fluency.md](docs/fluency.md) — why fluency is owned in-house; observable chain  
8. [docs/score-composition.md](docs/score-composition.md) — vendor scores + report composition contract  
9. [docs/missing-responses.md](docs/missing-responses.md) — unanswered items, retries, what the report does not flag  
10. [docs/lexicon-layer.md](docs/lexicon-layer.md) — supporting lexicon / morphology layer (shape only)  
11. [docs/failure-case-pronunciation-accent-channel.md](docs/failure-case-pronunciation-accent-channel.md) — field note: movie-like speech vs score; accent identity; channel/audio  
12. [docs/failure-case-vendor-fluency-insensitive.md](docs/failure-case-vendor-fluency-insensitive.md) — field note: vendor fluency barely moves under obvious disfluency  
13. [docs/limits.md](docs/limits.md) — what this repo will not claim  

---

## What is deliberately omitted

See [NOTICE.md](NOTICE.md). Especially: production weights, IELTS mapping as a product claim, dictionary dumps, audio, and vendor internals.

---

## Author

Applied psychology (assessment) background; content / assessment design on AI interview products.  
GitHub: [yuanlin-82](https://github.com/yuanlin-82)
