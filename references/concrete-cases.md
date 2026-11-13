# Concrete Case Patterns

Worked examples showing how to move from symptoms to a pattern (證/証), treatment, and prevention. Adapt to evidence; do not copy prescriptions without diagnosis.

## Case 1 — Inconsistent Answers Across Runs (Wind + Dryness)

**Presenting complaint**: Same question yields materially different answers; users lose trust.

**四診 evidence**
- 望: high output variance across 10 runs; retrieval returns 0–1 weak chunks for some runs.
- 聞: answers conflict on key facts; some include unsupported claims.
- 問: no prompt/config change; occurs on knowledge-heavy queries.
- 切: fixing retrieval to a known-good context reduces variance sharply.

**Pattern (證)**: Wind (instability) with Dryness (insufficient grounding), primary Spleen (retrieval/transformation) starving Heart (inference).

**Treatment**
- Root: improve retrieval coverage/chunking/ranking; ensure required sources present (治病求本, 扶正).
- Support: lower sampling randomness for factual tasks; require cite-or-abstain behavior (調和陰陽).
- Verify: variance and factuality on a fixed query set improve.

**Prevention (治未病)**: retrieval hit-rate and answer-consistency evals; alert on grounding drop.

---

## Case 2 — Answers Degrade Over Long Conversations (Dampness + Heat)

**Presenting complaint**: Early turns are good; later turns become verbose, confused, and off-topic.

**四診 evidence**
- 望: context length grows each turn; irrelevant history retained; output length increases.
- 聞: responses mix stale details with new request; coherence drops.
- 問: users report "it gets muddled after a while."
- 切: resetting/summarizing context restores quality; truncating noisy history helps.

**Pattern (證)**: Dampness (accumulation/pollution) leading to Heat (over-generation/divergence), involving Spleen (context assembly) and Heart.

**Treatment**
- Root: relevance-based memory/context selection, summarization, dedupe, turn/size budgets.
- Branch/acute: cap length and add stop/structure constraints for active sessions.
- Verify: multi-turn eval shows stable relevance and bounded length.

**Prevention**: context-growth metrics, long-horizon regression tests.

---

## Case 3 — Tool Calls Fail with Correct Reasoning (Lung/Cold)

**Presenting complaint**: Model explains the right action but tool execution fails or never completes.

**四診 evidence**
- 望: schema/validation errors and timeouts in traces; retries without progress.
- 聞: output intent is correct but formatted payload invalid or missing fields.
- 問: started after API/schema change.
- 切: replay with corrected schema succeeds; prompt-only changes do not.

**Pattern (證)**: Cold/stasis at Lung (interface/boundary) — contract mismatch blocking flow.

**Treatment**
- Root: align schemas/contracts, update tool specs, fix timeout/retry policy (治病求本).
- Support: structured outputs/validators; clearer tool descriptions.
- Verify: tool-call success rate and latency recover on replay set.

**Prevention**: contract tests, schema/version checks, integration monitors (Kidney).

---

## Case 4 — Confident but Wrong Summaries (Fire + Kidney Weakness)

**Presenting complaint**: Summaries sound authoritative yet contain fabricated details.

**四診 evidence**
- 望: no factuality eval or citation checks in pipeline; accuracy untracked over time.
- 聞: fluent, assertive claims not supported by sources.
- 問: high-stakes domain; users trusted outputs.
- 切: requiring evidence/citations and abstention reduces fabricated claims.

**Pattern (證)**: Fire (confident wrongness) in Heart, sustained by Kidney weakness (no baseline/eval/observability).

**Treatment**
- Acute: gate or label ungrounded claims; require evidence for high-risk outputs (急則治標).
- Root: add grounding, claim-evidence checks, calibration/factuality evals, traceability (標本兼治).
- Verify: factuality and calibration on domain eval set; incident rate drops.

**Prevention**: continuous factuality monitoring, golden sets, escalation for low evidence.

---

## Case 5 — Prompt "Fix" Breaks Other Tasks (Imbalance/Overacting)

**Presenting complaint**: A prompt tweak fixes one failure but degrades unrelated flows.

**四診 evidence**
- 望: target case improves; regression suite shows drops elsewhere.
- 聞: responses become over-constrained or miss nuance in other intents.
- 問: change optimized for a single report.
- 切: scoped prompt/routing restores both.

**Pattern (證)**: Local excess creating imbalance; Liver (flow/instruction) overacting on other subsystems.

**Treatment**
- Root: scope instructions by intent/route, modularize prompts, separate concerns (調和陰陽, 因地制宜).
- Verify: target and non-target evals both pass.

**Prevention**: broad regression coverage before prompt changes (治未病), change review by pattern.

## Using Cases

- Extract the **diagnostic move** (which 四診 evidence distinguished hypotheses), not just the fix.
- Note where multiple patterns coexist and which was primary.
- Record confidence and counter-evidence; update when new evidence appears.
