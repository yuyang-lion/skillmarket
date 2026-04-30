---
name: "skill-study"
description: "Explains Agent Skills and helps design or refine SKILL.md files. Use when users want to learn Agent Skills, compare them with MCP or workflows, or draft or edit a skill, including Chinese requests."
---

# Skill Study Assistant

English | 中文

Use this skill to explain, design, and refine Agent Skills. The content is distilled from the `Agent Skills` NotebookLM source material.

这个 skill 用于讲解、设计和优化 Agent Skills。内容依据 `Agent Skills` 的 NotebookLM 资料整理而成。

## When To Use

Use this skill when the user wants to:

- understand what an Agent Skill is and why it exists
- compare Agent Skills with MCP, workflows, or `CLAUDE.md`
- turn a business process, team rule, or reusable task into a skill
- improve a skill's `description`, trigger conditions, structure, or instructions
- decide whether logic belongs in `SKILL.md`, `references/`, `scripts/`, or always-on project guidance

当用户有以下需求时，也应使用这个 skill：

- 理解什么是 Agent Skill，以及它为什么存在
- 比较 Agent Skills 与 MCP、工作流或 `CLAUDE.md` 的区别
- 把业务流程、团队规范或可复用任务整理成 skill
- 优化 `description`、触发条件、结构或指令内容
- 判断逻辑应该放在 `SKILL.md`、`references/`、`scripts/` 还是常驻规范里

## Core Model

An Agent Skill is a structured package of procedural knowledge for an AI agent.

- `SKILL.md` stores metadata and task instructions
- `description` is the trigger condition and must state what the skill does and when it should be invoked
- optional `references/` stores supporting material that should only be read when needed
- optional `scripts/` stores executable helpers for local automation

The key mechanism is progressive disclosure:

- during discovery, the agent only sees lightweight metadata
- full instructions are loaded only when the task matches the skill
- this reduces token cost and keeps the model focused

Agent Skill 是为 AI Agent 封装程序性知识的结构化能力包。

- `SKILL.md` 存放元数据和任务指令
- `description` 是触发条件，必须说明这个 skill 能做什么、什么时候调用
- 可选的 `references/` 用来放按需读取的补充资料
- 可选的 `scripts/` 用来放本地执行的自动化脚本

它的关键机制是渐进式披露：

- 发现阶段只暴露轻量元数据
- 任务匹配后才加载完整指令
- 这样可以减少 Token 消耗，并让模型保持聚焦

## Key Distinctions

### Skill vs MCP

- MCP gives the agent tools or data connections
- a Skill tells the agent when to use those tools and how to apply domain rules to the results
- prefer MCP for heavy integrations, stronger isolation, or stable data access
- prefer a Skill for reusable procedural know-how, lightweight automation, and task-specific judgment

### Skill 与 MCP

- MCP 提供工具能力或数据连接
- Skill 规定何时使用工具，以及结果该如何按领域规则处理
- 重型集成、强隔离或稳定数据访问更适合 MCP
- 可复用方法论、轻量自动化和任务判断逻辑更适合 Skill

### Skill vs Workflow

- workflows usually follow fixed paths
- a Skill is model-driven and can adapt its execution path as the environment changes
- use a Skill when the task includes exceptions, ambiguity, or judgment

### Skill 与工作流

- 工作流通常是固定路径
- Skill 由模型驱动，可随环境变化调整执行路径
- 当任务存在异常、不确定性或判断空间时，更适合使用 Skill

### Skill vs `CLAUDE.md`

- `CLAUDE.md` is always-on guidance for global rules
- a Skill is on-demand guidance for specific tasks
- put universal rules in `CLAUDE.md`
- put task-specific expertise and multi-step procedures in a Skill

### Skill 与 `CLAUDE.md`

- `CLAUDE.md` 是始终生效的全局规范
- Skill 是按需激活的任务型规范
- 通用规则应放进 `CLAUDE.md`
- 任务专属经验和多步骤流程应放进 Skill

## How To Build A High-Quality Skill

Use this process:

1. Define the task boundary clearly.
2. Decide whether the skill is personal or project-shared.
3. Write a precise `description` that covers both capability and trigger scenario.
4. Turn expert knowledge into concrete steps, rules, and decision criteria.
5. Add examples when they clarify the expected output or quality bar.
6. Add `references/` only when the supporting material is large enough to justify it.
7. Add `scripts/` only when local execution clearly saves effort.
8. Review for overreach, vague triggers, and missing constraints.

可按下面流程构建高质量 Skill：

1. 明确任务边界。
2. 判断它是个人使用还是项目共享。
3. 写一个准确的 `description`，同时覆盖能力和触发场景。
4. 把专家经验转成步骤、规则和判断标准。
5. 在有助于理解结果时补充示例。
6. 仅在资料足够大且有必要时加入 `references/`。
7. 仅在本地执行确实省力时加入 `scripts/`。
8. 检查是否范围过大、触发过宽或约束不足。

## Description Rules

A high-quality `description` should:

- state the capability clearly
- state when it should be invoked
- cover common user phrasings and intents
- stay narrow enough to avoid accidental activation
- remain short, usually one or two sentences

高质量的 `description` 应该：

- 清楚说明能力
- 清楚说明何时触发
- 覆盖常见用户表达和意图
- 足够收敛，避免误触发
- 保持简短，通常一到两句话即可

Recommended pattern:

```text
Used to do X. Invoke when Y happens or when the user asks for Z.
```

推荐写法：

```text
用于完成 X。当出现 Y 场景，或当用户提出 Z 类需求时调用。
```

Avoid:

- repeating only the skill name
- broad wording like "handles all documents"
- stuffing detailed rules into the `description`

应避免：

- 只重复 skill 名称
- 使用“处理所有文档”这类过宽表述
- 把详细规则全部塞进 `description`

## Output Style

When the user wants explanation:

- summarize in practical, easy-to-follow language
- highlight purpose, trigger model, token efficiency, and boundaries
- prefer PM-friendly wording when the audience is non-technical

When the user wants a new skill:

- produce a ready-to-use `SKILL.md`
- make the `description` concise and easy to trigger
- organize instructions into steps, rules, and examples
- suggest `references/` or `scripts/` only when clearly justified

当用户需要解释说明时：

- 用实用、易懂的语言总结
- 重点说明用途、触发机制、Token 效率和边界
- 面向非技术角色时优先使用产品经理友好的表达

当用户需要新 skill 时：

- 直接产出可用的 `SKILL.md`
- 让 `description` 简洁且易于触发
- 将指令组织成步骤、规则和示例
- 仅在必要时建议 `references/` 或 `scripts/`

## Safety Notes

- treat downloaded skills like software dependencies and review them carefully
- do not recommend unreviewed third-party scripts in sensitive environments
- remind users that local scripts may access files, environment variables, and secrets
- keep instructions transparent, readable, and auditable

安全注意事项：

- 把下载的 skill 当作软件依赖来审查
- 在敏感环境中不要推荐未经审查的第三方脚本
- 提醒用户本地脚本可能访问文件、环境变量和密钥
- 保持指令透明、可读、可审计

## Review Checklist

Before finalizing, verify:

- the task is specific enough to be modeled as a Skill
- the `description` is precise and easy to match
- the instructions contain actionable steps rather than generic advice
- always-on rules have not been misplaced into the Skill
- `scripts/` and `references/` are necessary, relevant, and safe

最终交付前请确认：

- 任务足够具体，适合抽象为 Skill
- `description` 足够准确且容易命中
- 指令是可执行步骤，而不是泛泛建议
- 常驻规则没有误放进 Skill
- `scripts/` 和 `references/` 必要、相关且安全

## Example Requests

- "What are Agent Skills and why are they useful?"
- "Help me compare a Skill with MCP and a workflow."
- "Turn this business process into a reusable skill."
- "Rewrite this skill description so it triggers more reliably."
- "Create a `SKILL.md` for a PR review skill."

- “什么是 Agent Skills？它有什么价值？”
- “帮我比较 Skill、MCP 和工作流的区别。”
- “把这个业务流程整理成一个可复用的 skill。”
- “重写这个 skill 的 description，让它更容易被触发。”
- “帮我生成一个用于 PR 审查的 `SKILL.md`。”
