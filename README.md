# Solution Deck Planner

`solution-deck-planner` 是一个面向企业汇报与解决方案规划的 Agent Skill，支持 Codex、Claude Code 和 WorkBuddy。它能够读取项目资料、知识库、历史对话或已有 PPT，围绕汇报对象、决策目标和项目阶段，输出可直接进入 PPT 制作环节的完整方案。

当前版本：`v1.2.0`

## 适用场景

- 公司能力与产品能力介绍
- 客户项目解决方案
- 产品解决方案及市场教育材料
- CIO、EB、TB汇报材料
- 技术评审与业务共创材料
- 已有PPT的审核、重构和受众版本改编

其中：

- **EB（经济购买影响者）**：拥有最终资金审批和采购决策权。
- **TB（技术购买影响者）**：建立技术筛选标准，拥有技术推荐权和一票否决权。

## 核心能力

1. 发现并整理本地文件、项目目录、知识库和历史对话。
2. 形成项目情报底稿、汇报任务书和关键角色影响地图。
3. 建立统一内容母版，并针对不同受众派生版本。
4. 设计核心主张、消息地图、论证树和章节结构。
5. 输出逐页标题、内容、版式、图示、证据和讲述提纲。
6. 检查决策逻辑、证据质量、权限边界和现场异议。
7. 生成供人员阅读和PPT生成Skill执行的双格式交接包。

## 工作模式

- **快速规划**：背景明确、资料完整的轻量任务。
- **深度策划**：历史项目、重要决策或复杂解决方案。
- **现有材料优化**：审核、重构或改编已有PPT/PPTX。

深度策划包含四个确认节点：资料范围、项目情报、核心叙事和制作版本。

## Codex安装

### Windows

PowerShell执行：

```powershell
git clone https://github.com/lvjingyang10086/solution-deck-planner.git "$env:USERPROFILE\.codex\skills\solution-deck-planner"
```

安装到自定义共享目录：

```powershell
git clone https://github.com/lvjingyang10086/solution-deck-planner.git "D:\path\to\shared-skills\solution-deck-planner"
```

### macOS

终端执行：

```bash
git clone https://github.com/lvjingyang10086/solution-deck-planner.git "$HOME/.codex/skills/solution-deck-planner"
```

安装完成后，重新启动Codex或刷新技能列表。

## Claude Code安装

Claude Code采用相同的 `SKILL.md` 标准，可以直接使用本仓库，无需转换文件。官方说明见 [Claude Code Skills](https://code.claude.com/docs/en/skills)。

### Windows个人安装

在PowerShell中执行：

```powershell
git clone https://github.com/lvjingyang10086/solution-deck-planner.git "$env:USERPROFILE\.claude\skills\solution-deck-planner"
```

### macOS个人安装

在终端执行：

```bash
git clone https://github.com/lvjingyang10086/solution-deck-planner.git "$HOME/.claude/skills/solution-deck-planner"
```

### 项目级安装

在项目根目录执行：

```bash
git clone https://github.com/lvjingyang10086/solution-deck-planner.git ".claude/skills/solution-deck-planner"
```

个人安装对所有项目生效；项目级安装仅对当前项目生效。如果Claude Code会话启动时还不存在顶层Skills目录，安装后请重启Claude Code。

### 更新

进入安装目录并拉取最新版本：

```bash
git pull
```

## 使用方法

### Codex

显式调用：

```text
使用 $solution-deck-planner 帮我规划一份面向EB的项目解决方案汇报。
```

也可以直接描述任务：

```text
读取这个历史项目的资料，帮我规划一份面向CIO的20分钟汇报材料。
```

```text
审核这份PPT，将它重构为适合TB技术评审的版本。
```

### Claude Code

使用斜杠命令显式调用：

```text
/solution-deck-planner 帮我规划一份面向EB的项目解决方案汇报。
```

也可以直接用自然语言描述任务，Claude会在匹配Skill描述时自动调用：

```text
请读取当前项目资料，规划一份面向TB的技术评审材料。
```

`agents/openai.yaml`用于Codex界面展示，Claude Code会忽略该文件，不影响Skill运行。

## WorkBuddy安装与使用

WorkBuddy通过界面上传本地技能包。官方说明见 [WorkBuddy技能文档](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)。

### 安装步骤

1. 打开本仓库的 [Releases](https://github.com/lvjingyang10086/solution-deck-planner/releases)。
2. 下载最新版本的 `solution-deck-planner-vX.Y.Z.zip` 技能包。
3. 打开WorkBuddy侧边栏的“技能”页面。
4. 点击“添加技能”，选择“上传技能”。
5. 选择下载的ZIP技能包并等待安全检测和自动配置完成。
6. 在“已安装”中确认该Skill已经启用。

### 调用示例

安装后直接在WorkBuddy对话中描述任务：

```text
请使用solution-deck-planner，读取相关项目资料，规划一份面向EB的解决方案汇报。
```

```text
请审核这份PPT，并将它重构为适合TB技术评审的版本。
```

建议仅在需要规划或审核汇报材料时启用该Skill，以减少无关调用。安装第三方Skill前，应检查来源、权限申请和文件内容。

当资料不足、涉及历史项目或解决方案规划时，Skill会提示上传相关产品、解决方案、历史汇报或客户资料，也可以指定在线知识库或历史对话供其读取和整理。

## 标准输出

- 项目情报底稿
- 汇报任务书与成功标准
- 受众影响地图
- 一页执行摘要
- 核心主张与消息地图
- 章节框架和页面预算
- 逐页内容与页面架构
- 讲述提纲与关键问题库
- 证据、素材和权限清单
- PPT制作结构化任务包
- 项目记忆草案

只有通过终稿质量门槛后，Skill才会提示调用PPT生成Skill继续制作。

## 权限与数据原则

- 继承当前用户可访问的数据范围。
- 区分“可以分析”和“可以对外展示”。
- 不修改源文件、知识库或历史对话。
- 不虚构数据、案例、产品能力或引用。
- 对敏感信息执行脱敏、确认、限制或排除。

## 目录结构

```text
solution-deck-planner/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── audience-playbooks.md
    ├── content-and-evidence.md
    ├── examples.md
    ├── handoff-spec.md
    ├── intelligence-intake.md
    ├── narrative-patterns.md
    ├── permission-policy.md
    ├── quality-review.md
    └── slide-brief-schema.md
```

## 版本与更新

详细更新记录见 [CHANGELOG.md](CHANGELOG.md)。
