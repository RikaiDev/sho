# sho（證）

以「證／証（shō）」為核心的 LLM 系統型態診斷框架，靈感來自黃帝內經思想在日本漢方／東洋醫學語境中的系統觀。

`sho`（證/証）指透過四診綜合判讀所得到的整體狀態與型態：不是單一症狀或病名，而是身心／系統各部分相互關聯後呈現的全貌。本技能將此視角應用於 LLM 應用：提示詞與指令流程、模型推理、檢索與資料、工具／整合介面、評測與可觀測性。

> 此為工程分析的隱喻框架，**不是**醫療建議、診斷或治療。

## 功能

- 將 LLM 事件視為**系統型態**（失衡、滯塞、傳導）而非孤立症狀
- 以**四診**蒐證：望、聞、問、切
- 以**五臟**功能視角定位子系統，結合**六淫**失效型態與気・血・水、陰陽・虚實等流動／性質描述
- 依**論治**原則處置：治病求本、調和陰陽、標本緩急、因時因地制宜、治未病

## 安裝

```bash
cp -R sho ~/.agents/skills/sho
```

符合 [Agent Skills](https://agentskills.io) 結構（`SKILL.md`、`references/`、`agents/openai.yaml`）。

## 結構

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

## 驗證

```bash
# 可選：依 Agent Skills 規格檢查 frontmatter/命名
skills-ref validate ./sho
```

## 與既有技能關係

- **buddhist-method**：著重如何思考與查證；**sho**：著重用何種系統型態框架診斷（互補）。
- **software-engineer / engineering-principles**：負責執行與品質門檻；sho 補上 LLM 系統型態診斷。
- **clean-architecture**：聚焦程式碼結構；sho 聚焦應用／系統行為型態。

## 限制

- 屬隱喻而非等同；證據不符時不強行歸類，允許框架外的發現。
- 明確標示信心程度、證據缺口與可推翻診斷的條件。

## 授權

MIT（見 [LICENSE](LICENSE)）。
