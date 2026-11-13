# 四診 Diagnostic Workflow for LLM Debugging

四診 (four examinations) structures evidence gathering before and during diagnosis. Do not jump from a symptom to a treatment; form a pattern (證/証) from converging evidence.

## The Four Diagnostics

| Diagnostic | Traditional sense | LLM engineering practice | Artifacts |
|---|---|---|---|
| **望 Observation** | inspect appearance | Read what the system shows: logs, traces, metrics, configs, diffs, dashboards, token/latency stats | traces, timelines, dashboards, error rates, diffs, config snapshots |
| **聞 Listening/Smelling** | listen and attend to signals | Attend to outputs and signals: semantic quality, coherence, format, tone, consistency, error messages | sampled outputs, eval scores, schema/format checks, semantic comparisons |
| **問 Inquiry** | ask history and symptoms | Gather reports and probe intent: user feedback, reproduction steps, expectations, environment, recent changes, A-B/boundary tests | bug reports, repro cases, change history, test matrix, hypotheses tested |
| **切 Palpation** | touch/pulse/probe | Probe behavior directly: stress, replay, edge inputs, fault injection, controlled perturbations | replays from prod traces, fuzz/boundary inputs, load tests, isolation experiments |

## Workflow

1. **Presenting complaint** — capture the symptom, impact, frequency, first-seen time, and scope.
2. **望** — collect objective signals without altering the system; establish baseline and deviation.
3. **聞** — evaluate output quality against intent/contract/evidence; sample across cases, not a single anecdote.
4. **問** — elicit missing context (what changed, where it fails, for whom, under what inputs/configs).
5. **切** — run targeted probes to confirm/refute hypotheses; vary one factor at a time when possible.
6. **Synthesize pattern (證)** — name primary subsystem(s), mode(s), polarity (虚/実, 寒/熱), propagation, confidence, and gaps.
7. **Treat and re-examine** — apply intervention, then repeat relevant diagnostics to verify resolution and absence of new imbalance.

## Evidence Quality

- Prefer **reproducible** observations and **comparative** evidence (before/after, good/bad, control/variant).
- Record **absence** of evidence (what you could not observe) — often a Kidney/observability issue.
- Separate **signal from noise**: single-run flukes (Wind) vs consistent failures.
- Track **time and change**: correlate onset with deployments, data/model/prompt/config changes.

## Diagnostic Checklist

- [ ] Can I reproduce or replay the failure?
- [ ] Do I have traces/logs for a failing and a healthy case?
- [ ] Have I sampled enough outputs to judge consistency and quality?
- [ ] Do I know recent changes (prompt, model, data, tools, config, infra)?
- [ ] Have I probed boundaries (long context, missing retrieval, tool errors, adversarial/edge input)?
- [ ] What evidence would falsify my leading pattern?

## Mapping to Fixes

- 望 gaps → add tracing/metrics/logging (strengthen Kidney).
- 聞 failures → constrain/ground outputs, add semantic/format evals (Heart/Spleen/Lung).
- 問 ambiguity → clarify requirements, contracts, and test cases.
- 切 failures at edges → harden limits, retries, fallbacks, and guards.

## Caution

Do not over-test in production without safeguards. When palpation (切) carries risk, use offline replay, staging, or shadow evaluation first.
