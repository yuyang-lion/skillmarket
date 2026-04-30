---
name: "skill-study"
description: "Explains Agent Skills and helps design or refine SKILL.md files. Use when users want to learn Agent Skills, compare them with MCP or workflows, or draft or edit a skill."
---

# Skill Study Assistant

Use this skill to explain, design, and refine Agent Skills. The content is distilled from the `Agent Skills` NotebookLM source material.

## When To Use

Use this skill when the user wants to:

- understand what an Agent Skill is and why it exists
- compare Agent Skills with MCP, workflows, or `CLAUDE.md`
- turn a business process, team rule, or reusable task into a skill
- improve a skill's `description`, trigger conditions, structure, or instructions
- decide whether logic belongs in `SKILL.md`, `references/`, `scripts/`, or always-on project guidance

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

## Key Distinctions

### Skill vs MCP

- MCP gives the agent tools or data connections
- a Skill tells the agent when to use those tools and how to apply domain rules to the results
- prefer MCP for heavy integrations, stronger isolation, or stable data access
- prefer a Skill for reusable procedural know-how, lightweight automation, and task-specific judgment

### Skill vs Workflow

- workflows usually follow fixed paths
- a Skill is model-driven and can adapt its execution path as the environment changes
- use a Skill when the task includes exceptions, ambiguity, or judgment

### Skill vs `CLAUDE.md`

- `CLAUDE.md` is always-on guidance for global rules
- a Skill is on-demand guidance for specific tasks
- put universal rules in `CLAUDE.md`
- put task-specific expertise and multi-step procedures in a Skill

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

## Description Rules

A high-quality `description` should:

- state the capability clearly
- state when it should be invoked
- cover common user phrasings and intents
- stay narrow enough to avoid accidental activation
- remain short, usually one or two sentences

Recommended pattern:

```text
Used to do X. Invoke when Y happens or when the user asks for Z.
```

Avoid:

- repeating only the skill name
- broad wording like "handles all documents"
- stuffing detailed rules into the `description`

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

## Safety Notes

- treat downloaded skills like software dependencies and review them carefully
- do not recommend unreviewed third-party scripts in sensitive environments
- remind users that local scripts may access files, environment variables, and secrets
- keep instructions transparent, readable, and auditable

## Review Checklist

Before finalizing, verify:

- the task is specific enough to be modeled as a Skill
- the `description` is precise and easy to match
- the instructions contain actionable steps rather than generic advice
- always-on rules have not been misplaced into the Skill
- `scripts/` and `references/` are necessary, relevant, and safe

## Example Requests

- "What are Agent Skills and why are they useful?"
- "Help me compare a Skill with MCP and a workflow."
- "Turn this business process into a reusable skill."
- "Rewrite this skill description so it triggers more reliably."
- "Create a `SKILL.md` for a PR review skill."
