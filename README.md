# skill-study

English | [中文](#中文说明)

`skill-study` is a reusable Agent Skill for learning Agent Skills and drafting better `SKILL.md` files.

It helps users:

- understand what Agent Skills are and why they exist
- compare Skills with MCP, workflows, and `CLAUDE.md`
- turn business processes or team rules into reusable skills
- improve descriptions, trigger conditions, and instruction structure

## Highlights

- Single-file distribution: only one `SKILL.md` is kept in the repository
- Easy installation: copy one file into `.trae/skills/skill-study/`
- GitHub-friendly layout: optimized for browsing, reading, and reuse
- Bilingual documentation: suitable for both Chinese and English readers

## Repository Structure

```text
skill-study/
├── README.md
├── CHANGELOG.md
├── LICENSE
└── SKILL.md
```

## Files

- `SKILL.md`: the only skill file, ready to copy into a Trae skills directory
- `README.md`: installation guide and project overview
- `CHANGELOG.md`: release notes and version history
- `LICENSE`: repository license

## Install

### Project Scope

```bash
mkdir -p .trae/skills/skill-study
cp SKILL.md .trae/skills/skill-study/SKILL.md
```

### User Scope

```bash
mkdir -p ~/.trae/skills/skill-study
cp SKILL.md ~/.trae/skills/skill-study/SKILL.md
```

## Trigger Summary

This skill is designed to activate when users ask to:

- learn Agent Skills
- compare Skills with MCP or workflows
- draft or edit a skill
- improve a skill description so it triggers more reliably

## Suggested GitHub Topics

If you want better GitHub discoverability, add topics like:

- `agent-skill`
- `ai-agent`
- `prompt-engineering`
- `skill-market`
- `trae`

## Suggested GitHub About Text

Short description:

```text
A reusable Agent Skill for learning Agent Skills and drafting better SKILL.md files.
```

Optional Chinese description:

```text
一个用于学习 Agent Skills 并帮助编写更好 SKILL.md 的可复用 skill。
```

## Release Notes

See [CHANGELOG.md](file:///Users/fanfan/Documents/trae_projects/skill/skill-study/CHANGELOG.md) for the current release history.

## 中文说明

`skill-study` 是一个可复用的 Agent Skill，用于学习 Agent Skills，并帮助编写或优化 `SKILL.md`。

它适合以下场景：

- 理解什么是 Agent Skill，以及它为什么存在
- 比较 Skill、MCP、工作流和 `CLAUDE.md` 的差异
- 将业务流程或团队规范整理成可复用的 skill
- 优化 `description`、触发条件和指令结构

## 主要特点

- 单文件发布：仓库里只保留一份 `SKILL.md`
- 安装简单：复制一个文件即可完成安装
- 适合 GitHub 展示：目录更清晰，便于阅读和分享
- 中英双语：方便公开发布和团队传播

## 安装方式

### 项目级安装

```bash
mkdir -p .trae/skills/skill-study
cp SKILL.md .trae/skills/skill-study/SKILL.md
```

### 用户级安装

```bash
mkdir -p ~/.trae/skills/skill-study
cp SKILL.md ~/.trae/skills/skill-study/SKILL.md
```

## 适用触发场景

当用户提出以下需求时，这个 skill 更容易被触发：

- 学习 Agent Skills
- 比较 Skill 与 MCP 或工作流
- 起草或修改一个 skill
- 优化 skill 的描述，使其更容易被正确触发

## 发布建议

- 在 GitHub 仓库中添加 topics 以提高可发现性
- 每次更新 `SKILL.md` 后同步更新 `CHANGELOG.md`
- 如果未来增加 `scripts/` 或 `references/`，建议先进行安全审查
