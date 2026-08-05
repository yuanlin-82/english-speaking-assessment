# Field note: Vendor “fluency” that barely moves

## Stakeholder / design symptom

Product reports needed a **fluency** axis that tracking experts could trust. Multiple speech vendors marketed **English fluency** (or fluency-like) scores. Field checks showed the same practical failure: scores **did not track obvious fluency changes** in the speech itself, and tended to sit **falsely high**.

This note explains why this stack treats **fluency as an in-house evidence chain** (rate / pause / repair → perceived fluency)—see [fluency.md](fluency.md)—instead of buying a vendor fluency head.

Vendor **names are omitted on purpose**. The point is the **failure pattern**, not a vendor review blog.

---

## Market check, not a one-off demo

We exercised **every vendor we could reach that claimed to offer English fluency assessment** for this kind of use. None produced fluency scores we could trust for hiring reports.

What made the result feel “thick” rather than anecdotal:

| Observation | Why it matters |
| --- | --- |
| **Cross-vendor** | Failure was not one bad API—it repeated across the marketed set. |
| **Similar shape** | Scores looked **alike in behavior**: weak separation across fluency levels, **false highs**, hard to obtain a genuinely low band. |
| **Opaque stack** | When asked how fluency was computed, answers were **secrecy**, or the counterpart **could not explain** the method. That blocks scientific debugging from the buyer side. |

**Suspicion (not proven):** the behavioral likeness makes it reasonable to wonder whether several offerings share **related technical lineage** or similar proxies. We cannot verify that from the outside; opacity is part of the product risk.

So the decision was not “vendor A failed, try vendor B.” It was: **do not outsource the fluency construct** for this report.

---

## What we tried (simple, harsh probe)

Vendors’ evaluation surfaces often included **several elicitation modes** (for example: read a **word**, read a **sentence**, read a **paragraph**). This product is for **hiring interviews**, not classroom/teaching drills, so checks focused on **paragraph** mode—the closest match to continuous speech in interview oral tasks.

On the **same paragraph text** (held constant so content was not the confound), the tester deliberately varied delivery, including:

- smooth, natural pacing  
- **very slow** speech  
- **unnatural pauses**  
- **stutter-like repetition** / broken delivery  

Because those deliveries were **intentionally controlled**, a large drop in perceived fluency was **expected on the ear**—not an ambiguous rating debate. Vendor fluency-like scores still **moved only a little**.

Even when delivery was pushed into a **rarely heard, strongly disfluent** style, scores could still sit in a **high band** on a ten-point-style scale (for example remaining **above about 7**). Under normal product conditions it was unclear how a candidate would obtain a **genuinely low** fluency score from those fields.

That is a measurement failure for hiring use: a dimension that cannot go low when speech is badly non-fluent mostly **compresses everyone upward**.

---

## Why this matters more than “the number looks precise”

- HR and candidates read one decimal place as truth.  
- A sticky high fluency score can **wash out** real delivery problems, or make the whole oral report look “fine” when pronunciation or content is the real issue.  
- If **every marketed fluency head** fails the same ear-test, swapping logos does not fix the construct—you need **observables you control** (rate / pause / repair) and expert alignment.  
- ASR can further hurt **repair** features (missed hesitations / false starts). In our fitted mapping those repair terms were **weak predictors** anyway, so the practical fluency axis leaned more on **rate / pause**; ASR-vs-repair remains a known nuisance, not the main reason we rejected vendor fluency heads.

---

## Design takeaways

1. **Treat “we sell English fluency” as a claim to falsify**, not a feature to paste into the report.  
2. **Do not let a vendor fluency field silently become the report fluency axis.**  
3. Prefer **observable families** that move when delivery moves; **map features → perceived fluency** (in-house, often regression-strength mapping)—do not buy an opaque fluency float.  
4. Opacity (“confidential” / non-technical sales) is itself a reason **not** to stake hiring decisions on that number.  
5. Keep stress-test notes in the methodology layer; do not publish vendor names, score dumps, or production thresholds.

**Related lesson from the literature (not a vendor claim):** long-standing automated speaking pipelines already argued for **fluency-related features from recognition output, then statistical mapping to human scores**—not for trusting an unexplained product label named “fluency.” Our probes falsified the latter; our build follows the former. See also [fluency.md](fluency.md).

---

## What this note is not

- Not a league table or attack on a named company.  
- Not proof that all vendors share one codebase—only that **marketed fluency scores** failed similarly in our probes.  
- Not a full psychometrics write-up (no RMSE tables here).  
- Not a claim that regression is universally optimal—only that, among mappings we tried for this product, it held up.  
- Channel/audio effects on **pronunciation** are separate: [failure-case-pronunciation-accent-channel.md](failure-case-pronunciation-accent-channel.md).
