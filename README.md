# skill-study

`skill-study` explains Agent Skills and helps users design, review, and refine `SKILL.md` files.

It is intended for situations where someone wants to:

- learn what Agent Skills are and how they work
- compare Skills with MCP, workflows, or `CLAUDE.md`
- draft a new skill from a business process or team rule
- improve a skill's trigger description, structure, or instructions

## Repository Structure

This repository is organized for both GitHub browsing and direct installation:

```text
skill-study/
├── README.md
├── LICENSE
├── SKILL.md
└── .trae/
    └── skills/
        └── skill-study/
            └── SKILL.md
```

## Files

- `SKILL.md`: a top-level copy for easy reading on GitHub
- `.trae/skills/skill-study/SKILL.md`: the install-ready skill file
- `README.md`: usage and installation guide
- `LICENSE`: repository license

## Install

### Project Scope

Copy the skill into a project's `.trae` directory:

```bash
mkdir -p .trae/skills/skill-study
cp SKILL.md .trae/skills/skill-study/SKILL.md
```

### User Scope

Copy the skill into your user-level skills directory:

```bash
mkdir -p ~/.trae/skills/skill-study
cp SKILL.md ~/.trae/skills/skill-study/SKILL.md
```

If you clone this repository directly, you can also copy the prebuilt install path:

```bash
cp -R .trae/skills/skill-study <target-path>
```

## Trigger Summary

The skill is designed to activate when users ask to:

- learn Agent Skills
- compare Skills with MCP or workflows
- draft or edit a skill
- improve a skill description for better triggering

## Publishing Notes

- Keep `SKILL.md` and `.trae/skills/skill-study/SKILL.md` in sync
- Update `README.md` whenever the skill scope or installation steps change
- Review any future `scripts/` or `references/` additions before publishing
