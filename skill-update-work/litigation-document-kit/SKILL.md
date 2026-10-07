---
name: litigation-document-kit
description: Generate or update common Chinese litigation, arbitration, and criminal case document sets from a case folder and existing templates. Use when asked to draft 起诉状, 答辩状, 仲裁申请书, 质证意见, 授权委托书, 所函, 法定代表人证明书, 地址确认书, 委托代理协议, 保全申请, 取保候审申请, 法律意见书, or prepare a complete filing/response document package.
---

# Litigation Document Kit

## Workflow

1. Identify case type and stage from folder name, filenames, and any provided facts: 民间借贷, 买卖/定作/承揽合同, 劳动仲裁, 物业/租赁, 执行/执行异议, 离婚/析产, 刑事辩护/会见等.
2. Search the same workspace for close templates before drafting from scratch. Prefer templates from the same year, same case type, same court/arbitration context, or same client.
3. Extract stable variables:
   - 当事人名称/身份信息/统一社会信用代码/住所.
   - 法定代表人/联系人/送达地址.
   - 代理律师、律所、律师证/所函相关信息.
   - 案号、法院/仲裁委、案由、阶段、日期.
   - 诉请/仲裁请求/答辩请求 and key facts.
4. Generate only the documents the user asked for, or propose a complete suite when they ask for "一套材料".
5. Preserve local drafting conventions: filename prefixes, Chinese punctuation, court style, signature blocks, and existing wording for the same client.
6. Mark unknown facts with clear placeholders such as `【待补充：...】`; do not invent dates, amounts, ID numbers, addresses, or case numbers.

## Template Format Rule

When a workspace template exists, document formatting must stay consistent with the original template.

- Create the new Word document from a copy of the closest `.docx` template whenever possible; replace content inside the copied template rather than rebuilding styles from scratch.
- Preserve the template's fonts, font sizes, bolding, paragraph alignment, first-line indents, line spacing, page margins, table structure, table borders, merged cells, title style, signature block alignment, and spacing.
- For each document type, use its matching template: 起诉状 uses the 起诉状 template, 财产保全申请书 uses the 保全申请 template, 证据目录/证据清单 uses the evidence catalog template, 送达地址确认书 uses the court address confirmation template, and so on.
- If rebuilding is unavoidable, first inspect the template's paragraph/run/table formatting and copy those exact settings into the generated file.
- After generation, check for both content errors and format drift: old names/case types left from the template, changed fonts, changed title size, missing bold labels, broken table merges, or altered page layout.
- Do not simplify court forms or table-based templates into plain prose unless the user explicitly asks.

## Common Suites

### 民商事立案

起诉状, 证据目录, 授权委托书, 所函, 法定代表人证明书/身份证明, 地址确认书, 保全申请书 if needed, 主体材料清单.

### 应诉答辩

答辩状, 质证意见, 证据目录/反证目录, 授权委托书, 所函, 地址确认书, 庭审提纲.

### 劳动仲裁

仲裁申请书或答辩状, 证据目录, 工资/考勤/社保明细说明, 授权委托书, 法定代表人证明书, 地址确认书, 质证意见.

### 刑事案件

委托书, 介绍信, 会见手续, 取保候审申请书, 法律意见书, 辩护词, 阅卷摘要, 退赔/谅解材料清单.

## Drafting Rules

- Treat the output as a lawyer-reviewed draft under Chinese mainland law; do not replace the lawyer's final legal judgment.
- Before drafting from multiple case materials, build a material checklist and identify which files were actually read.
- Separate client statements, evidenced facts, reasonable inferences, unverified facts, legal conclusions, and strategic allegations. Formal pleadings may advocate a position but must not present unsupported inference as established fact.
- Analyze each material claim through claim basis, required elements, evidence, burden of proof, likely defenses, and legal consequence. Do not accept a conclusion merely because the user proposed it.
- If the requested claim, cause of action, party, jurisdiction, amount, interest start date, or evidence purpose is unsupported, state that the conclusion is insufficient and use a placeholder or safer alternative.
- Verify current legal provisions, procedural rules, court information, and public entity information when they may have changed. Never invent provisions, case numbers, quotations, or company details.
- Use the user's role to frame claims: 原告/申请人 focus on elements, damages, jurisdiction, evidence; 被告/被申请人 focus on抗辩, 事实争议, 责任范围, 程序问题.
- Keep factual statements traceable to available materials; cite filenames when preparing internal drafts.
- For formal documents, create editable Word documents when requested or when the user asks for "文书"; a Markdown draft is acceptable for review-only requests.
- Maintain separate draft and final files. Use filenames like `起诉状-当事人-整理稿.docx` until the user approves finalization.
- When using prior templates, update all names, case numbers, courts, dates, signature blocks, and party roles; explicitly check for leftover names from the source template.
- For Word outputs based on a template, formatting fidelity is part of the deliverable, not a polish step. Prefer exact template continuity over newly designed formatting.
- Use natural, restrained, specific Chinese legal prose. Remove empty introductions, slogan-like conclusions, mechanical parallelism, excessive “首先/其次/最后”, and formulaic phrases such as “值得注意的是”“不难发现”“由此可见”.
- When the workspace contains `禁用表达.md` or an equivalent style file, read and obey it before drafting or revising.

## Output

Return:

- Generated file paths or draft text.
- A short list of placeholders needing confirmation.
- A checklist of companion materials still needed before submission.
