# Glossary (術語對照)

Engineering-oriented meanings for terms used in `sho`. Terms are analytical metaphors, not medical claims.

## Core

| Term | 日本語/中文 | Romaji/Pinyin | Engineering meaning in sho |
|---|---|---|---|
| 證 / 証 | しょう | shō / zhèng | Holistic presenting pattern: whole-system state inferred from evidence, not a single symptom/label. |
| 四診 | 望・聞・問・切 | shishin / sìzhěn | Four diagnostics: observation, listening/output review, inquiry, palpation/probing. |
| 望診 | ぼうしん | bōshin / wàng | Observation of objective signals (logs, traces, metrics, diffs, config). |
| 聞診 | ぶんしん | bunshin / wén | Listening/attending to outputs and signals (quality, consistency, format, errors). |
| 問診 | もんしん | monshin / wèn | Inquiry: history, reports, expectations, repro, changes, tests. |
| 切診 | せっしん | sesshin / qiè | Palpation/probing: replay, stress, boundary and fault perturbation. |
| 辨證 / 弁証 | べんしょう | benshō / biànzhèng | Pattern differentiation: synthesizing evidence into a pattern diagnosis. |
| 論治 | ろんち | ronchi / lùnzhì | Treatment planning/principles applied according to the diagnosed pattern. |
| 方証相対 | ほうしょうそうたい | hōshō-sōtai | Matching an intervention/formula to the presenting pattern (pattern-intervention fit). |

## Flow and qualities

| Term | 日本語/中文 | Romaji/Pinyin | Engineering meaning in sho |
|---|---|---|---|
| 氣 | き | ki / qì | Flow/control/signal/orchestration and driving capacity. |
| 血 | けつ | ketsu / xuè | Nourishing substance: grounded content/knowledge feeding outputs. |
| 水 | すい | sui / shuǐ | Medium/fluids: context and distribution; accumulation or insufficiency. |
| 陰陽 | いんよう | in'yō / yīnyáng | Polarity/balance (e.g. restraint vs activation, determinism vs variability). |
| 虛實 | きょじつ | kyojitsu / xūshí | Deficiency vs excess (capacity/signal/load/behavior). |
| 寒熱 | かんねつ | kannetsu / hánrè | Cold/heat dynamics: stasis-contraction vs agitation-expansion. |
| 表裏 | ひょうり | hyōri / biǎolǐ | Surface/interior: boundary manifestation vs deeper cause. |

## Functional subsystems (五臟 view)

| Term | 日本語/中文 | Romaji/Pinyin | Engineering mapping (functional lens) |
|---|---|---|---|
| 五臟 | ごぞう | gozō / wǔzàng | Five functional subsystems used to localize and relate behavior. |
| 肝 | かん | kan / gān | Flow/regulation: prompt & instruction flow, routing, orchestration. |
| 心 | しん | shin / xīn | Inference/reasoning coherence and calibration. |
| 脾 | ひ | hi / pí | Transformation/nourishment: retrieval, data, context assembly, grounding. |
| 肺 | はい | hai / fèi | Interface/boundary: tools, APIs, formats, transport, I/O contracts. |
| 腎 | じん | jin / shèn | Foundation/essence: evaluation, observability, baselines, traceability. |
| 五行 | ごぎょう | gogyo / wǔxíng | Relational heuristics (generation/overacting) for propagation hypotheses. |

## Failure modes (六淫 view)

| Term | 日本語/中文 | Romaji/Pinyin | Engineering signal |
|---|---|---|---|
| 六淫 | りくいん | rikuin / liùyín | Six exogenous influence patterns as failure-mode qualities. |
| 風 | ふう | fū / fēng | Wind: variability, non-determinism, sudden change. |
| 寒 | かん | kan / hán | Cold: contraction, stasis, truncation, stall. |
| 暑/熱 | しょ/ねつ | sho/netsu / shǔ/rè | Heat: excess, agitation, over-generation, runaway divergence. |
| 濕 | しつ | shitsu / shī | Dampness: accumulation, stickiness, pollution, carryover. |
| 燥 | そう | sō / zào | Dryness: insufficiency, brittleness, missing evidence/context. |
| 火 | か | ka / huǒ | Fire: flaring, confident wrongness, damaging escalation. |

## Treatment and prevention

| Term | 日本語/中文 | Romaji/Pinyin | Engineering meaning in sho |
|---|---|---|---|
| 治病求本 | ちびょうきゅうほん | chibyō kyūhon / zhìbìng qiúběn | Treat root cause, not only symptoms. |
| 急則治標，緩則治本 | — | — / jí zé zhì biāo, huǎn zé zhì běn | Stabilize urgent impact first; correct root when conditions allow. |
| 標本兼治 | ひょうほんけんち | hyōhon kenchi / biāoběn jiānzhì | Treat branch and root together when feasible. |
| 扶正祛邪 | ふせいきょじゃ | fusei kyoja / fúzhèng qūxié | Strengthen sound function/paths; remove harmful inputs or behaviors. |
| 治未病 | ちみびょう | chimibyō / zhì wèibìng | Prevent before incident: evals, monitors, guards, hygiene. |
| 養生 | ようじょう | yōjō / yǎngshēng | Ongoing maintenance to preserve healthy system balance. |

## 備註
- 日本漢方用語 (e.g. 証/shō, 氣血水) and classical Chinese sources inform the framing; this glossary fixes **how sho uses the terms for LLM engineering**.
- When a term adds no diagnostic value, prefer a plain mechanism description.
