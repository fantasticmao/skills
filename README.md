# FantasticMao's Skills

[![skills.sh](https://skills.sh/b/fantasticmao/skills)](https://skills.sh/fantasticmao/skills)
[![license](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

English | [简体中文](README_ZH.md)

## What is this

FantasticMao's Skills provides custom agent skills. Each skill is a `SKILL.md` document that states how a recurring task should be carried out, and a coding agent with skill support loads it on demand. It ships instructions only: no executable tool, dependency or MCP server.

## Features

- **[readme-style](skills/readme-style)** — Writes and refines a README with a consistent voice, structure and formatting, including bilingual versions.

## Download and Install

```bash
npx skills add fantasticmao/skills
```

```bash
# Install for every project of the current user
npx skills add fantasticmao/skills -g

# Install a single skill
npx skills add fantasticmao/skills -s readme-style

# List the available skills without installing
npx skills add fantasticmao/skills -l
```

> [!NOTE]
> The command installs into the current project by default, and `-g` installs into the user directory instead. `-a` limits the target agents, and `npx skills update` pulls later revisions.

## Quick Start

An agent matches the request against the `description` of every installed skill and applies the matching one. Naming the skill makes the choice explicit:

```text
Rewrite the README of this project with the readme-style skill.
```

## License

FantasticMao's Skills is released under the [MIT License](LICENSE).
