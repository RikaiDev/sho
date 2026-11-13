# sho (證)

Pattern-based diagnosis for LLM applications, inspired by 黃帝內經-informed systemic thinking as received in Japanese Kampo/東洋医学.

`sho` (證/証, *shō*) names a holistic presenting pattern: the state of the whole system across interacting parts, determined through observation and inquiry rather than by an isolated symptom label. This skill applies that lens to LLM systems—prompt flow, model behavior, retrieval/data, integration boundaries, and evaluation/observability.

> Analytical metaphor for engineering. Not medical advice, diagnosis, or treatment.

## What it does

- Frames LLM incidents as **system patterns** (imbalance, blocked flow, propagation) instead of one-off symptoms
- Guides evidence gathering with **四診** (observation, listening, inquiry, palpation)
- Maps concerns to functional subsystems (**五臓** view), failure modes (**六淫**), and flow qualities (気・血・水, 陰陽・虚実)
- Proposes treatments by principle (**論治**): root cause, balance, adaptation, and prevention (治未病)

## Install

```bash
# install into your agent skills directory (example)
cp -R sho ~/.agents/skills/sho
```

Follows the [Agent Skills](https://agentskills.io) layout (`SKILL.md`, `references/`, `agents/openai.yaml`).

## Layout

```
sho/
├── SKILL.md
├── README.md
├── README.th.md
├── LICENSE
├── agents/
│   └── openai.yaml
├── assets/
│   ├── diagnosis-checklist.md
│   └── pattern-report.md
└── references/
    ├── concrete-cases.md
    ├── glossary.md
    ├── liuyin-failures.md
    ├── siduan-diagnosis.md
    ├── wuzang-systems.md
    └── zhinang-principles.md
```

## Validation

```bash
# optional: validate frontmatter/naming per Agent Skills spec
skills-ref validate ./sho
```

## Relationship

- **buddhist-method** — how to think/investigate; **sho** — what systemic pattern framework to diagnose with (complementary).
- **software-engineer / engineering-principles** — execution and quality gates; sho adds LLM system-pattern diagnosis.
- **clean-architecture** — code structure; sho focuses on application/system behavior patterns.

## Limits

- Metaphor, not literal equivalence. Do not force evidence into categories; allow outside-framework findings.
- State confidence, gaps, and what would change the diagnosis.

## License

MIT (see [LICENSE](LICENSE)).
