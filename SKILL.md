---
name: solution-deck-planner
description: Plan decision-ready presentation and solution-deck architectures from project context, files, knowledge bases, historical conversations, public web intelligence, or existing PPT/PPTX materials. Use when users need to research a target organization or its executives, or create, restructure, review, or adapt company capability presentations, product or project solutions, executive briefings, technical reviews, business proposals, or slide-by-slide PPT plans for CIOs, economic buyers (EB), technical buyers (TB), technical experts, business experts, or mixed audiences. Produces organization intelligence, narrative strategy, deck framework, per-slide content and layout briefs, evidence and permission checks, speaker notes, objections, and a structured handoff for a PPT-generation skill.
---

# Solution Deck Planner

Turn project intelligence into a persuasive, decision-oriented presentation plan. Plan the deck and its production handoff; do not generate a PPTX unless the user explicitly invokes a separate PPT-generation skill.

## Select the operating mode

Infer the mode and briefly state the choice. Let the user override it.

- **Quick planning**: Use for a clear, bounded request with enough context and no important historical material.
- **Deep planning**: Use for historical or continuing projects, important customer decisions, solution planning, multiple stakeholders, or substantial source material.
- **Existing-deck optimization**: Use when reviewing, restructuring, or adapting an existing PPT/PPTX.
- If uncertain, ask only questions that materially affect the plan; ask no more than three at a time.

## Guide source intake conditionally

Show the following guidance only when information is insufficient, the work concerns a historical/continuing project, or the user requests product/project solution planning:

> 如果你有相关产品、解决方案、历史汇报或客户项目资料，可以直接上传文件或提供所在目录。  
> 如果相关内容已沉淀在知识库、在线文档或历史对话中，也可以提供链接或名称。我会先完成资料读取与知识整理，经你确认后，再结合项目具体信息、汇报对象和决策目标进行规划输出。

Discover candidate sources first, summarize what is available, and obtain user confirmation before broad reading. Never modify source files, project knowledge, online knowledge bases, or historical conversations. Read [intelligence-intake.md](references/intelligence-intake.md) for deep or source-heavy work.

When the target organization is identifiable, offer a focused public web-intelligence search covering its AI, digitalization, intelligent transformation, strategic goals, major initiatives, and relevant executive statements. Confirm the organization identity, time range, and search scope before browsing unless the user explicitly asks for the search. Read [web-intelligence.md](references/web-intelligence.md).

## Run the planning workflow

Use four confirmation gates in deep mode. In quick mode, compress gates while preserving decision quality.

### Gate 1: Confirm sources and project intelligence

Build a concise project intelligence brief covering facts, stage, history, stakeholders, needs, commitments, objections, competitors, public organization intelligence, evidence, conflicts, sensitive information, and open questions. Extract the customer's own terminology. Distinguish facts, executive statements, opinions, inferences, and assumptions.

### Gate 2: Confirm the assignment and narrative

Define the minimum assignment:

- Who is the audience?
- Why are they being briefed?
- What should they decide or do?

Also define the success criterion, project stage, meeting context, time/page budget, decision barrier, mandatory content, exclusions, and confidentiality. Read [audience-playbooks.md](references/audience-playbooks.md) and [narrative-patterns.md](references/narrative-patterns.md).

Create a message map before a page list:

`core claim -> up to three reasons -> evidence -> requested action`

### Gate 3: Confirm the management view

Build a unified content master, then derive audience versions from it. Show the proposed chapter flow, page budget, and management view with page number, conclusion-led title, page purpose, and primary audience. Do not bury the user in detailed slide briefs before this view is approved.

Use the solution closure map:

`customer problem -> root cause -> solution capability -> scenario -> business value -> evidence`

Remove or move to the appendix any capability that does not answer a relevant problem. Flag major problems with no solution response. Read [content-and-evidence.md](references/content-and-evidence.md).

### Gate 4: Confirm the production version

Expand the approved management view into production-ready slide briefs. Include slide purpose, target cognitive change, key message, 3-5 supporting points, evidence, layout, visual focus, visual type, assets, speaker outline, transition, permissions, and readiness status. Read [slide-brief-schema.md](references/slide-brief-schema.md).

## Review quality and objections

Before declaring a final version:

- Check decision alignment, narrative continuity, audience fit, solution closure, evidence quality, page expressibility, permissions, and sensitive information.
- Generate high-risk audience questions with response direction and evidence location.
- Classify findings as must fix, recommended, or production-stage refinement.
- Use [quality-review.md](references/quality-review.md) for the scorecard, final gate, and exception handling.

## Deliver two synchronized outputs

Produce:

1. **Human-readable plan**: assignment, audience map, message map, framework, management view, detailed slide briefs, one-page executive summary, speaker outlines, key questions, evidence/assets list, quality summary, and project-memory draft.
2. **Structured handoff**: machine-readable slide records and deck-level constraints for a PPT-generation skill. Follow [handoff-spec.md](references/handoff-spec.md).

Use one content master for all audience variants. Record whether each item is retained, compressed, rewritten, removed, or moved to the appendix.

For representative cross-scenario behavior, read [examples.md](references/examples.md). Treat the examples as patterns, never as fixed outlines.

## Enforce permissions and source integrity

- Inherit the current user's role, department, and source visibility boundaries.
- Treat permission to analyze as distinct from permission to present.
- Require explicit authorization for cross-department, confidential, customer, personnel, pricing, or competitive information.
- Preserve source, date, confidence, and evidence status for consequential claims.
- Never invent data, customer cases, commitments, product capabilities, or citations.
- Propose external research scope before browsing unless the user explicitly asks to search.
- Read [permission-policy.md](references/permission-policy.md) whenever sensitive or multi-source information is involved.

## Keep the experience light

- Show only the current stage and next decision.
- Reuse discovered information instead of asking for it again.
- Offer practical shortcuts such as “采用建议”, “跳过”, or “直接出框架”.
- In deep mode, show progress as the current confirmation gate out of four.
- Generate a project-memory draft, but do not persist it unless the user explicitly requests that action.

Only after the final gate passes and no critical gap remains, end with this exact prompt:

> 终稿已经形成，你可以直接调用PPT生成Skill进行输出。
