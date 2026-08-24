# Rating rubric

Score each dimension from 0 to 5 using the anchors below. Record the raw score, weight, and evidence. Weighted score = the sum of `(raw score / 5) × weight`, rounded to the nearest whole number.

| Dimension | Weight | What it measures |
| --- | ---: | --- |
| Realness and verifiability | 25 | Whether claims are anchored in inspectable implementation, reproducible behavior, provenance, and evidence rather than presentation. |
| Practical usefulness | 25 | Whether a defined user can solve a real task with clear inputs, outputs, setup, and limitations. |
| Stability and maintainability | 20 | Whether the project has sane failure handling, dependency discipline, testing, documentation alignment, and a credible maintenance path. |
| Trust and safety | 15 | Whether the actual risk surface—permissions, data handling, supply chain, network access, or dangerous operations—is understood and bounded. A verified absence of a risk surface is positive evidence. |
| Project health | 15 | Whether recent, meaningful maintenance, issue responsiveness, versioning, and governance support continued use. |

## Dimension anchors

Use the closest supported anchor; interpolate only when the evidence justifies it.

- **5 — strong:** direct evidence shows this area consistently meets the stated purpose; notable limitations are documented and bounded.
- **4 — good:** the core is credible and usable, with minor evidence gaps or manageable weaknesses.
- **3 — mixed:** a real core exists, but gaps would require a pilot, review, or local hardening before reliance.
- **2 — weak:** claims are only partly substantiated, or important operational evidence is missing.
- **1 — very weak:** little trustworthy evidence supports the claim, or evidence indicates serious fragility.
- **0 — absent or contradicted:** no relevant evidence exists, the claim is demonstrably false, or a critical concern prevents meaningful use.

Score evidence quality separately as rating confidence:

- **High:** current source and representative behavior/tests were inspected; major claims have primary evidence.
- **Medium:** source and documentation were inspected, but behavior, dependencies, or operations were only partly verified.
- **Low:** review relied mostly on documentation, metadata, a partial snapshot, or inaccessible external systems.

## Star mapping

| Weighted score | Rating | Decision posture |
| ---: | --- | --- |
| 90–100 | 5.0 stars | Strong candidate to adopt after normal fit checks. |
| 80–89 | 4.5 stars | High-quality; validate environment-specific assumptions. |
| 70–79 | 4.0 stars | Solid; pilot before broad reliance. |
| 60–69 | 3.5 stars | Promising but requires targeted validation or hardening. |
| 50–59 | 3.0 stars | Mixed; use only for a constrained pilot. |
| 40–49 | 2.5 stars | Material gaps; watch for evidence or improvement. |
| 30–39 | 2.0 stars | Weak evidence or significant shortcomings; avoid for important use. |
| 20–29 | 1.5 stars | Not credible enough for normal adoption. |
| 10–19 | 1.0 stars | Serious concerns outweigh demonstrated value. |
| 0–9 | 0.5 stars | No trustworthy basis for use. |
| 0 (exception only) | 0.0 stars | Malicious, unavailable, or no evaluable artifact; avoid. |

Issue 0 stars only when the artifact is malicious, unavailable, or provides no evaluable artifact at all. A low-confidence review must visibly say that its star rating is provisional.

## Report template

```markdown
## Verdict

**3.5 / 5 stars — Pilot first (medium confidence).** One sentence explaining the decision.

Reviewed: `<URL or path>` at `<commit/release/date>`.

| Dimension | Score | Weight | Evidence-based reason |
| --- | ---: | ---: | --- |
| Realness and verifiability | x/5 | 25 | ... |
| Practical usefulness | x/5 | 25 | ... |
| Stability and maintainability | x/5 | 20 | ... |
| Trust and safety | x/5 | 15 | ... |
| Project health | x/5 | 15 | ... |
| **Weighted total** |  | **xx/100** |  |

### Evidence highlights
- **FACT:** ... (source)
- **INFERENCE:** ... (why)

### Risks and unknowns
- **UNKNOWN:** ...

### Recommendation
Adopt / Pilot first / Watch / Avoid for now. Next smallest check: ...
```
