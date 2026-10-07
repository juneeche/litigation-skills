---
name: litigation-skills
description: Unified Chinese litigation workflow skill suite for case analysis, legal research, evidence-to-strategy reasoning, material audits, evidence catalogs, pleadings, legal writing, hearing prep, and archive checks. Use when asked to handle Chinese litigation/arbitration case folders, analyze client evidence, research Chinese law or cases, formulate诉讼方案, draft or review 起诉状/答辩状/证据目录/质证意见/代理词/法律分析, prepare庭前摘要, organize案件材料, reduce AI-like legal prose, or choose the right litigation workflow skill.
---

# Litigation Skills

## Purpose

Use this as the main entry point for litigation work. It routes the task to the right litigation workflow and keeps the core method consistent:

```text
客户目标 -> 法律关系定性 -> 请求权/抗辩要件 -> 证据功能分类 -> 诉讼方案 -> 文书/证据/质证/庭前/归档
```

Before substantive work, read `references/legal-work-rules.md` completely and apply it as the shared role, Chinese-law, material-handling, citation, independent-review, and writing-style standard. If the workspace contains `禁用表达.md` or an equivalent style file, read it before drafting or rewriting.

## Routing

Choose the workflow by user intent:

| User intent | Primary workflow |
| --- | --- |
| 从客户证据形成诉讼方案、起诉/答辩思路、证据目录、质证要点 | Evidence to strategy |
| 检查案件文件夹是否缺材料 | Case material audit |
| 整理证据、生成证据目录、规划合并顺序 | Evidence catalog and merge |
| 生成起诉状、答辩状、授权、所函、地址确认等一套文书 | Litigation document kit |
| 开庭前快速阅读案件并生成摘要、争议焦点、发问和质证提纲 | Hearing prep brief |
| 结案后检查归档、命名和缺失材料 | Case archive normalizer |
| 中国内地法律研究、案例分析、法律文章或降AI味 | Apply the shared legal work rules, then use the closest workflow |

When the task involves strategy or evidence reasoning, always start with Evidence to strategy before drafting documents.

## Core Evidence-To-Strategy Workflow

1. Identify the client role and objective: plaintiff, defendant, applicant, respondent, third party, criminal suspect/defendant, execution applicant, or interested party.
2. Decide the legal relationship: sale, loan, labor, entrustment/agency, contracting, lease, partnership, equity holding, execution, tort, criminal defense, or mixed.
3. Break down the required elements for the claim or defense.
4. Classify all important evidence into six functions:
   - 法律关系.
   - 履行事实.
   - 金额计算.
   - 违约/抗辩.
   - 因果与损失.
   - 程序节点.
5. Build an evidence matrix and mark strength, gaps, and burden of proof.
6. Convert the matrix into:
   - 起诉状: 关系 + 履行 + 金额 + 违约 + 诉请.
   - 答辩状: 对方要件拆解 + 事实重构 + 程序/金额/举证抗辩.
   - 证据目录: 每项证据对应一个法律要件证明目的.
   - 质证意见: 三性 + 证明目的攻击 + 我方替代事实 + 举证责任.
7. Give next actions: 补证, 保全, 反诉, 和解, 庭前准备, 执行, 归档.

## Output Template

Unless the user asks for a narrow deliverable, output:

```markdown
**一、案件定位**

**二、客户目标**

**三、证据矩阵**
| 要件 | 现有证据 | 证明力 | 缺口 | 文书用途 |
| --- | --- | --- | --- | --- |

**四、诉讼方案**

**五、文书结构**

**六、证据目录/证明目的**

**七、质证和抗辩要点**

**八、下一步待办**
```

## References

Read `references/legal-work-rules.md` for mandatory shared legal-work rules.

Read `references/evidence-to-strategy-methodology.md` for the full distilled methodology from the user's case folder.

## Guardrails

- Do not invent facts, dates, amounts, party identities, case numbers, or court information.
- Preserve source filenames when citing evidence.
- Mark uncertain items as `待核对`.
- Treat AI output as lawyer work product draft; formal submissions require lawyer review.
- Separate user statements, evidenced facts, reasonable inferences, unverified facts, legal conclusions, and strategic assumptions.
- Verify current legal authorities and public information; never fabricate provisions, case numbers, quotations, or sources.
- Challenge unsupported user conclusions and provide a safer formulation or evidence path.
- Use restrained, specific Chinese legal prose; remove boilerplate, marketing language, and mechanical AI-style transitions.
