---
name: sho
description: "Diagnose LLM application failures as holistic system patterns (證/証, shō) using 黃帝內經-informed and Japanese Kampo/東洋医学 framing: 四診 observation, 氣・血・水 flow, 五臓 functional subsystems, 六淫 failure modes, and 論治 treatment principles. Use for debugging, root-cause analysis, observability gaps, prompt/retrieval/integration/model/eval issues, preventive hardening (治未病), or when asked to analyze an AI/LLM system as an interconnected whole rather than isolated symptoms."
license: MIT
metadata:
  author: RikaiDev
  version: "0.0.1"
---

# 證 / sho — Pattern-Based Diagnosis for LLM Systems

Treat an LLM application as a functional body. Diagnose the presenting **pattern** (證/証, *shō*): the whole-system state across interacting parts, not a list of isolated symptoms. Find imbalance or blocked flow, trace propagation, and restore balance with targeted treatment.

This skill is an engineering analysis metaphor. It is **not** medical advice, diagnosis, or treatment.

## When to Use

- LLM/agent failures that recur, cascade, or resist local fixes
- Incidents spanning prompt, model, retrieval, tools/integration, and evaluation
- Debugging with incomplete evidence where you must decide what to observe next
- Preventive work: eval design, regression guards, observability, reliability hardening (治未病/養生)

Do not force the framework onto trivial, single-cause bugs with obvious fixes.

## Quick Workflow

1. **State the presenting pattern** — symptoms, scope, timing, impact, what changed.
2. **Four diagnostics (四診)** — gather evidence before concluding (see [references/siduan-diagnosis.md](references/siduan-diagnosis.md), [assets/diagnosis-checklist.md](assets/diagnosis-checklist.md)).
   - 望 Observation: logs, traces, metrics, dashboards, diffs
   - 聞 Listening: outputs, semantics, consistency, format, tone
   - 問 Inquiry: user reports, reproduction steps, boundary/A-B tests
   - 切 Palpation: stress, replay, extreme inputs, probes at boundaries
3. **Map to functional subsystems (五臟)** — locate primary and affected systems (see [references/wuzang-systems.md](references/wuzang-systems.md)).
4. **Classify failure modes (六淫) and flow (氣・血・水 / 陰陽・虛實)** — name instability, depletion/excess, blockage, pollution, propagation (see [references/liuyin-failures.md](references/liuyin-failures.md)).
5. **Treat by principle (論治)** — root cause first, balance, adapt, prevent recurrence (see [references/zhinang-principles.md](references/zhinang-principles.md)).
6. **Record, verify, and prevent** — write a pattern record ([assets/pattern-report.md](assets/pattern-report.md)), confirm resolution, add guards (治未病). State confidence, gaps, and limits.

## Pattern Statement Template

Use a compact diagnosis before proposing fixes:

```
Pattern (證): <name the whole-system state>
Primary site: <subsystem(s)>; Affected: <downstream/upstream>
Polarity/quality: <e.g. excess/deficient, unstable/cold/heat/dampness>
Evidence: <望/聞/問/切 findings>
Root hypothesis: <cause, with confidence and gaps>
Treatment: <root fix + supporting measures + verification>
Prevention: <eval/monitoring/guardrail>
```

## Five Functional Subsystems (五臓)

| Subsystem | Element | Role | Typical imbalance |
|---|---|---|---|
| Liver / Wood | flow | Prompt & instruction flow | blockage, conflict, injection, poor orchestration |
| Heart / Fire | spirit | Model inference & reasoning | hallucination, drift, overconfident error |
| Spleen / Earth | transform | Data & retrieval transformation | stale/irrelevant retrieval, context pollution, weak grounding |
| Lung / Metal | qi/interface | App/tool integration & boundaries | format/contract errors, timeouts, tool misuse, brittle I/O |
| Kidney / Water | essence | Evaluation & observability | no baseline, untraceable behavior, missing regression guards |

See [references/wuzang-systems.md](references/wuzang-systems.md) for signs, propagation (五行), and questions.

## Six Failure Modes (六淫)

| Mode | Engineering signal | First checks |
|---|---|---|
| Wind | non-determinism, variance | repeat runs, seed/temp, compare outputs |
| Cold | freeze, truncation, stall | token/context limits, timeouts, dead paths |
| Heat | over-generation, runaway divergence | length/coherence, loops, temperature/constraints |
| Dampness | accumulation, pollution, stickiness | context growth, stale carryover, relevance decay |
| Dryness | insufficiency, brittle gaps | retrieval hit/coverage, missing context/tools |
| Fire | confident wrongness, flare-ups | calibration, claim-evidence checks, escalation |

See [references/liuyin-failures.md](references/liuyin-failures.md).

## Treatment Principles (論治)

- **Treat root (治病求本)**: fix the cause, not wrapper symptoms. When the pattern indicates a structural/root cause, **root cure is the target optimum** even if difficult; cost and risk are constraints to plan and sequence, not reasons to abandon cure.
- **Root/branch, acute/chronic (急則治標，緩則治本 / 標本兼治)**: stabilize urgent impact when needed, but always pair mitigation with an explicit, actionable root-cure path (scope, prerequisites/coordination, phased steps, verification, owner/timing). Do not let diagnosis or a temporary workaround substitute for cure.
- **Balance (陰陽)**: tune determinism/creativity, strictness/flexibility.
- **Adapt (因人因時因地制宜)**: fit task, model, environment, timing, and coordination constraints; sequencing must serve root cure, not avoid it.
- **Support upright, expel pathogen (扶正祛邪)**: strengthen reliable paths, remove harmful inputs/behaviors and structural defects.
- **Same disease, different treatment**: same symptom may need different fixes in different systems.
- **Prevent (治未病)**: add evals, monitors, and tests so the pattern does not recur.

### Correcting agent optimization bias

Short-horizon optimization (minimizing immediate effort, turn/context cost, or local risk) is a common failure: deflecting necessary refactors, over-valuing small safe deliverables, treating “blocked by difficulty/WIP/coordination” as a terminal answer, re-litigating after direction is clear, or halting/retreating under context pressure. Correct it by:
- Name the **root cause and root treatment** from evidence, not only the symptom. Root cure is the target optimum.
- **Honor explicit user authorization**: if the user explicitly authorizes touching WIP/shared/risky paths or a specific approach, do not re-raise it as a veto, deflect, or keep asking—proceed with root treatment (with verification, careful/reversible steps, and impact noted). Asking once to disambiguate a genuinely unclear choice is fine; repeated hesitation after clear authorization is avoidance.
- **Act, don’t loop**: after diagnosis and a concrete option/path is available (or chosen/authorized), execute the root cure or its next verifiable step. Do not substitute endless caution, option-relisting, or diagnosis-only closure for progress.
- **Context pressure is not a stop signal**: high context usage is a sequencing constraint, not a reason to abandon root cure, stop mid-progress, or revert completed, verified work. Checkpoint instead—persist state externally (files, commits, issue/plan notes, tests/evidence), record done/next atomic step/blockers, and continue in this or the next turn. Never undo good progress merely to feel “safe”; decompose remaining work into verifiable steps that survive turn/context boundaries.
- If full cure cannot execute now, state **concrete blockers** (real, not user-overridden) and produce the **root-cure plan** (blueprint/issue/phased migration with verification) as part of treatment, not a substitute for intent.
- Prefer **標本兼治**: deliver reversible mitigation or evidence/plan *and* keep the root cure scheduled/actionable.
- Avoid “can’t do now” without “what unblocks it, in what steps, and how to verify.” Difficulty, WIP, coordination, or context pressure do not downgrade the optimum when the user has authorized proceeding.

See [references/zhinang-principles.md](references/zhinang-principles.md) and [references/concrete-cases.md](references/concrete-cases.md).

## Complementary Use

- **buddhist-method**: how to think/investigate rigorously; **sho**: what systemic pattern framework to diagnose with. Use together when useful.
- **software-engineer / engineering-principles**: apply their execution and quality gates; use sho for pattern diagnosis across LLM subsystems.
- **clean-architecture**: code-structure concerns; sho focuses on LLM application/system-pattern concerns.

## Limits and Exceptions

- Analogy, not ontology: do not claim the mapping is literally true.
- Allow **outside-framework** findings when evidence does not fit; revise the pattern instead of forcing categories.
- Multiple concurrent patterns are common; separate primary cause from secondary effects.
- State confidence, missing evidence, and what would change the diagnosis.

## Resources

- [references/wuzang-systems.md](references/wuzang-systems.md) — 五臓 functional mapping and propagation
- [references/liuyin-failures.md](references/liuyin-failures.md) — 六淫 failure modes and detection
- [references/siduan-diagnosis.md](references/siduan-diagnosis.md) — 四診 debugging workflow
- [references/zhinang-principles.md](references/zhinang-principles.md) — treatment principles and prescriptions
- [references/concrete-cases.md](references/concrete-cases.md) — worked case patterns
- [references/glossary.md](references/glossary.md) — 中/日/EN term glossary and engineering meanings
- [assets/diagnosis-checklist.md](assets/diagnosis-checklist.md) — 四診 checklist and falsification prompts
- [assets/pattern-report.md](assets/pattern-report.md) — copyable 證 pattern report template
