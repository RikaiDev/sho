# 論治 Treatment Principles for LLM Systems

Apply treatment (論治) only after forming a pattern (證/証) from 四診 evidence. Prefer the smallest intervention that addresses the root pattern, then verify and prevent recurrence.

## Core Principles

| Principle | Meaning | LLM practice | Anti-pattern |
|---|---|---|---|
| **治病求本** (treat the root) | Address cause, not only manifestation | Fix prompt/data/model/tool/eval/structural cause; remove propagation source. When evidence shows a structural root cause, root cure is the target optimum even if difficult | Patching symptoms/wrappers while cause remains; declaring "too hard/WIP/risky now" without a root-cure path |
| **調和陰陽** (harmonize/balance) | Restore dynamic balance | Balance determinism vs creativity, strictness vs flexibility, latency vs depth | Maximizing one dimension until the system destabilizes |
| **扶正祛邪** (support upright, expel pathogenic) | Strengthen healthy function, remove harm | Improve grounding, contracts, and tests; remove bad data/instructions/unsafe paths and structural defects | Adding complexity without removing the harmful input/behavior |
| **急則治標，緩則治本** (acute: branch; chronic: root) | Stabilize now, correct later when needed | Mitigate user impact first (fallback, rollback, guard), then execute root-cause repair | Root-cause-only response during active incident, or a permanent band-aid that never reaches root cure |
| **標本兼治** (treat root and branch) | Combine when feasible | Ship safe mitigation **and** an explicit, actionable root-cure plan/execution with verification and sequencing | Treating mitigation, diagnosis, or a blueprint as a substitute for root cure; deferring cure indefinitely |
| **因人因時因地制宜** (adapt to context) | Treatment fits conditions | Choose by task, model, domain, user risk, environment, timing, coordination/capacity constraints | Using constraints as justification to avoid cure rather than to sequence it; one-size-fits-all fixes |
| **同病異治 / 異病同治** (same disease different treatment / different diseases same treatment) | Pattern, not label alone, drives treatment | Same symptom (e.g. hallucination) may need different fixes; different symptoms may share a root | Copying a prior fix because the surface symptom looks similar |
| **治未病** (treat before illness) | Prevent and catch early | Evals, regression tests, monitoring, alerts, canaries, data/prompt hygiene | Relying on incident response instead of feedback loops |

## Correcting agent optimization bias

A common failure mode is **short-horizon optimization**: preferring actions that minimize immediate effort, turn/context cost, or local risk (small deliverables, diagnosis-only closure, deflecting refactors, repeated caution, premature stop/retreat) over actions that resolve the diagnosed root cause. In sho, this is a distorted optimization target.

- **True optimum**: restore system balance by treating the evidenced root cause (治病求本). Difficulty, size, coordination cost, or context budget does not negate the root optimum—it defines the plan and sequencing.
- **Honor explicit user authorization**: if the user explicitly authorizes touching WIP/shared/risky paths or choosing a root-cure approach, that authorization removes the "I must not" blocker. Do not re-litigate, deflect, or treat coordination as a veto; proceed with the root treatment (note impact, use verification and careful/reversible steps). Asking once to disambiguate a genuinely unclear choice is fine; asking again after clear authorization/direction is avoidance.
- **Act, don’t loop**: once diagnosis is evidenced and a path is available or authorized, execute the next verifiable root-cure step. Do not substitute option-relisting, repeated warnings, or diagnosis-only closure for progress.
- **Context pressure is not a stop signal**: high or rising context usage (e.g. "N% used") can induce risk-averse "anxiety"—a bias to halt, summarize, or revert. Treat it as a sequencing/checkpoint constraint, not a reason to abandon root cure, stop mid-progress, or undo completed, verified work. **Checkpoint protocol:** persist state externally (save files, commits, issue/plan/checklist updates, test evidence), record what is done, the next atomic verifiable step, and any real blockers; then continue this turn where possible or hand off cleanly to the next. Decompose work so each step leaves durable evidence. Never revert good progress to regain perceived safety.
- **Do not** treat "difficult", "WIP/conflict", "cross-cutting", "not finishable now", or "context is high" as reasons to abandon, deny, or silently avoid root cure. Treat them as constraints to sequence (因時因地制宜, 標本兼治)—or as non-blocking when the user has authorized proceeding.
- **When full cure is not immediately executable**: provide reversible/urgent mitigation if needed **and** a concrete root-cure path—blueprint or issue with evidenced diagnosis, scope, prerequisites/unblockers, phased steps, verification/acceptance, and ownership/timing. State only **real** blockers (not user-overridden, not mere context pressure); do not substitute the plan for intent to cure.
- **Avoid proxy closure**: "I diagnosed it", "I wrote a note", "context is full so I stopped", or "I reverted to be safe" is not cure unless paired with preserved progress and committed next steps toward the root treatment.
- **Name the trade-off honestly**: if you choose branch-first or checkpoint, record why, what root work remains, what was persisted, and what condition/step triggers continuation. Difficulty and context budget are planning inputs, not terminal answers.

## Prescription Templates

Use explicit, testable prescriptions:

```
Intervention: <change>
Target: <subsystem/mode/root>
Rationale: <why this addresses the pattern>
Expected effect: <observable improvement>
Risks/side effects: <possible new imbalance>
Verification: <望/聞/問/切 checks, metrics, cases>
Rollback: <how to revert if worsened>
```

### By Pattern Quality

- **Wind (instability)**: constrain sampling/config, stabilize prompts/routes, add consistency checks; verify with repeated-run variance.
- **Cold (stasis/truncation)**: raise/reshape limits, fix timeouts/dead paths, chunk or stream; verify completion and latency.
- **Heat (runaway/excess)**: add budgets/stop conditions, tighten schemas, lower agitation; verify length/coherence/loops.
- **Dampness (pollution/accumulation)**: trim/dedupe/re-rank context, reset carryover, improve relevance; verify grounding and drift over turns.
- **Dryness (insufficiency)**: improve retrieval/tool coverage and sources, ask/collect missing inputs; verify evidence sufficiency.
- **Fire (confident wrongness)**: require evidence/citations/checks, calibrate, gate high-risk claims; verify factuality and calibration.

## Dosing and Sequencing

- Change **one lever at a time** when diagnosing; bundle only for urgent mitigation with clear rollback.
- Prefer **reversible** interventions first.
- After each change, re-examine (四診): did the primary pattern ease? did a secondary imbalance appear?

## Preventive Regimen (治未病 / 養生)

- Maintain baselines and golden cases (Kidney).
- Add monitors for known modes (variance, truncation, relevance, calibration).
- Keep prompts/data/contracts clean; review regularly to prevent dampness/dryness.
- Document patterns and fixes so future incidents start from evidence, not guesswork.

## Limits

State uncertainty and trade-offs. A successful treatment in one environment (因地) or task (因人) may fail in another; carry forward the pattern and evidence, not just the prescription.
