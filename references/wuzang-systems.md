# 五臟 Functional Subsystems for LLM Applications

Map an LLM application to five cooperating functional subsystems (五臟). This is a **functional/relational** view (藏象), not a claim about literal organs. Use it to locate where a pattern (證/証) originates, how it propagates, and what to strengthen.

## Subsystem Map

| Subsystem | Element | Core function | LLM mapping | Healthy signs | Imbalance signs |
|---|---|---|---|---|---|
| **Liver (肝)** | Wood | Free flow, regulation | Prompt & instruction flow, routing, planning, orchestration | Clear instructions, smooth task decomposition, coherent control flow | Conflicting prompts, instruction blockage/injection, brittle routing, oscillating plans |
| **Heart (心)** | Fire | Spirit/consciousness, coherence | Model inference & reasoning | Grounded, coherent, calibrated responses | Hallucination, drift, inconsistency, overconfident wrong answers |
| **Spleen (脾)** | Earth | Transformation, nourishment | Data ingestion, retrieval, chunking, context assembly | Relevant, fresh, well-transformed context | Retrieval misses, stale/irrelevant data, context pollution, poor grounding |
| **Lung (肺)** | Metal | Governs qi, interface/boundary | Tools, APIs, UI, formats, auth, transport | Reliable contracts, clean I/O, graceful timeouts/retries | Format/schema errors, tool misuse, timeouts, integration breakage, boundary leaks |
| **Kidney (腎)** | Water | Stores essence, foundation | Evaluation, observability, baselines, memory of quality | Traces/metrics, baselines, regression tests, reproducibility | No baseline, blind spots, untraceable behavior, regressions undetected |

## Flow Qualities (気・血・水) as a Lens

- **氣 (qi/flow)** — control, signaling, orchestration, responsiveness. Stagnation → blocked or erratic flow (Liver/Lung issues). Deficiency → weak drive/coverage.
- **血 (blood/nourishment)** — substantive content and grounded knowledge feeding outputs. Deficiency/stasis → thin, stale, or poorly circulated information (Heart/Spleen).
- **水 (water/fluids)** — context and medium distribution (buffers, memory, hydration of prompts with evidence). Stasis/pollution → accumulation and swelling of irrelevant context; deficiency/dryness → brittle gaps.

Use these as descriptive qualifiers alongside 五臟 localization, not as a separate rigid taxonomy.

## Propagation (五行) Heuristics

Relations suggest how imbalance can spread; treat as hypotheses to verify with evidence.

- **Generating (相生)**: Wood→Fire→Earth→Metal→Water→Wood (flow enables inference → produces/needs transformed data → yields interfaces/results → feeds evaluation/essence → supports future flow).
- **Overacting/insulting (相剋失調)**: a stressed subsystem may over-constrain or destabilize another (e.g. rigid prompts blocking useful model behavior; poor eval allowing bad retrieval to persist).

Examples:
- Spleen (retrieval) deficiency starves Heart (inference) → plausible-sounding but ungrounded output.
- Lung (integration/format) failure blocks free flow (Liver) despite good prompts/model.
- Kidney (observability) weakness lets any other imbalance persist unnoticed.

## Diagnostic Questions

- **Liver/flow**: Are instructions coherent, prioritized, and reachable? Any conflict, injection, or routing loop?
- **Heart/inference**: Is reasoning consistent and calibrated? Does output follow evidence?
- **Spleen/transformation**: Is retrieved/assembled context relevant, fresh, sufficient, and clean?
- **Lung/interface**: Do schemas, tools, APIs, and formats hold? Where do boundaries fail or retry?
- **Kidney/foundation**: What baseline, traces, and evals exist? Can we reproduce and compare?

## Outside the Map

If evidence points to infrastructure, product policy, data governance, or human-process causes outside these five, record them explicitly rather than forcing a 五臟 label. The map is for LLM application behavior patterns.
