# 四診診斷檢查表

Use before concluding a pattern (證/証). Record evidence and absence of evidence.

## Intake
- [ ] Presenting symptom, impact, scope, frequency, first-seen time captured
- [ ] Recent changes identified (prompt/model/data/retrieval/tools/config/deploy/infra)
- [ ] Reproduction conditions known (or explicitly unknown)

## 望 Observation
- [ ] Failing vs healthy/baseline case compared (logs, traces, metrics, dashboards)
- [ ] Errors, latencies, token/context usage, stop reasons, retries/timeouts reviewed
- [ ] Relevant diffs/config snapshots/version identifiers collected
- [ ] Absence noted: signals not observable or not instrumented

## 聞 Listening
- [ ] Outputs sampled across multiple cases/runs (not a single anecdote)
- [ ] Checked semantics, factual/claim-evidence fit, consistency, format/contract, tone
- [ ] Variance vs consistency assessed (Wind signal?)

## 問 Inquiry
- [ ] User/report expectations and failure criteria clarified
- [ ] Boundary/A-B cases or hypotheses elicited
- [ ] Environment/task/model/context differences recorded

## 切 Palpation
- [ ] Reproduction or replay attempted (offline/staging/shadow when risky)
- [ ] One-factor perturbations where feasible (sampling, context, retrieval, tools, version)
- [ ] Boundaries probed (long context, missing/irrelevant retrieval, tool errors, edge/adversarial input)
- [ ] Production-risk safeguards considered before probing

## Synthesis (證)
- [ ] Primary subsystem(s) and propagation identified (五臟/氣・血・水) with evidence
- [ ] Failure mode(s) and qualities named (六淫, 陰陽・虛實・寒熱・表裏) — or marked outside-framework
- [ ] Root hypothesis stated separately from symptoms
- [ ] Confidence level stated (high/medium/low)
- [ ] Gaps and missing evidence listed
- [ ] Alternative hypotheses considered and compared

## Falsification / decision quality
- [ ] **What evidence would falsify or materially change this diagnosis?**
- [ ] Smallest verifying test or measurement defined
- [ ] Acute mitigation vs root treatment sequenced (急則治標，緩則治本 / 標本兼治) where relevant
- [ ] **Root-cure path defined** (治病求本): if not executable now, concrete blockers + actionable phased plan/verification/owner-timing recorded (not diagnosis-only closure)
- [ ] Short-horizon avoidance checked: difficulty/WIP/coordination/context pressure treated as sequencing constraints, not a reason to abandon root cure
- [ ] **Explicit authorization honored**: if user authorized WIP/shared/risky scope or a path, proceeded with root treatment (not re-litigated/deflected); only real, non-overridden blockers recorded
- [ ] **Context-pressure checkpoint** (if context high): no revert of verified progress; state persisted externally with done/next atomic step/blockers and continuation trigger

## After treatment
- [ ] 重新執行相關四診以驗證是否解除型態
- [ ] 未觀察到新的失衡／迴歸（或已記錄）
- [ ] 已加入預防措施（評測、監控、護欄、例行維護 — 治未病）
- [ ] Root cure resolved or actively scheduled with evidence-backed plan (no indefinite deferral without unblockers)
