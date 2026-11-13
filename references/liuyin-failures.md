# 六淫 Failure Modes for LLM Applications

Use 六淫 (six external pathogenic influences) as descriptive labels for recurring failure **qualities** in LLM systems. A single incident may show multiple modes; identify primary and secondary modes from evidence.

## Mode Map

| Mode | Quality | LLM signal | Typical evidence (四診) | First checks |
|---|---|---|---|---|
| **Wind (風)** | mobile, changeable, sudden | Non-deterministic output; unstable behavior across runs | 望 variance in metrics/traces; 聞 inconsistent answers; 切 repeated runs diverge | Repeat N times, compare; check temperature/top_p/seed; detect prompt-order sensitivity |
| **Cold (寒)** | contraction, stasis, slowing | Freeze, truncation, stall, blocked progress | 望 timeouts/token caps/hangs; 聞 cut-off or empty output; 切 boundary-length probes | Token/context limits, stop reasons, timeouts, dead branches, rate limits |
| **Heat (熱)** | excess, agitation, expansion | Over-generation, verbosity, runaway divergence, loops | 望 long outputs/looping traces; 聞 incoherent or inflated text; 切 stress prompts | Max tokens, loop detection, temperature/constraints, guardrails, stop conditions |
| **Dampness (湿)** | heavy, sticky, turbid accumulation | Context pollution, carryover, relevance decay, sludge | 望 growing context/retrieval noise; 聞 muddled/irrelevant answers; 問 "it got confused over time" | Context window growth, memory/session carryover, retrieval relevance & dedupe, chunk quality |
| **Dryness (燥)** | insufficiency, brittleness, lack of moisture | Missing information, brittle gaps, failed grounding | 望 low retrieval hit/coverage; 聞 vague or hedged gaps; 切 remove/withhold context | Retrieval coverage/hit rate, source availability, tool access, required fields present |
| **Fire (火)** | intense, flaring, damaging | Confident wrongness, sharp escalation, harmful certainty | 聞 assertive but incorrect claims; 望 calibration/accuracy gaps; 問 high-impact user trust | Claim-evidence alignment, confidence calibration, factuality checks, escalation/safety gates |

## Polarity and Intensity (陰陽・虚実・寒熱)

Qualify modes to sharpen the pattern (證):
- **虛/實 (deficiency/excess)**: too little capacity/signal vs overwhelming load or overactive behavior.
- **寒/熱 (cold/heat)**: stalled/contracted vs agitated/expansive dynamics.
- **表/裏 (surface/interior)**: boundary/interface manifestation vs deep subsystem cause.

Example: "Wind with interior deficiency" — variance rooted in weak grounding/eval rather than sampling alone.

## Detection Playbook

1. **Establish a baseline**: known-good prompt/input/model/version/config if available.
2. **Reproduce and vary one factor**: sampling, context size, retrieved docs, tools, model/version.
3. **Measure**: variance, length, latency, truncation, retrieval relevance, factual/format pass rate.
4. **Correlate**: map mode to subsystem (五臟) and propagation path.
5. **Disconfirm**: test an alternative mode/hypothesis before committing.

## Common Combinations

- **Wind + Dryness**: unstable answers because grounding is sparse (inference varies over thin evidence).
- **Dampness + Heat**: polluted, growing context drives verbose or runaway output.
- **Cold + Lung/interface**: apparent "freeze" caused by timeout/contract failure at boundaries.
- **Fire + Kidney weakness**: confident errors persist because eval/observability cannot catch them (治未病 gap).

## Limits

Modes are lenses for communication and search, not proof. When a mode label adds no predictive or diagnostic value, drop it and describe the mechanism directly.
