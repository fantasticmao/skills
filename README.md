# Skills

[![skills.sh][badge-skills]][skills-sh] [![license][badge-license]][license]

English | [简体中文][readme-zh]

## What is this

This repository collects the agent skills FantasticMao uses in daily development. Each skill is a `SKILL.md` document that states how a recurring task should be carried out, and any coding agent with skill support loads it on demand. The repository provides instructions only: it ships no executable tool, dependency or MCP server.

## Skills

- **[readme-style][skill-readme-style]** — Writes and refines a README with a consistent voice, structure and formatting, including bilingual versions.

## Install

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
> The command installs into the current project by default, and `-g` installs into the user directory instead. Use `-a` to limit the target agents, and `npx skills update` to pull later revisions.

## Quick Start

An agent matches the request against the `description` of every installed skill and applies the matching one on its own. Naming the skill makes the choice explicit:

```text
Rewrite the README of this project with the readme-style skill.
```

## How it works

Every skill lives in its own directory under `skills/`, holding a `SKILL.md` whose YAML frontmatter carries a `name` and a `description`. This flat layout is one of the locations the [skills CLI][skills-cli] discovers, so installation copies the directory into the skills path of each selected agent. The frontmatter stays in the agent context while the body is read only once a request matches the description, which keeps an idle skill inexpensive.

[badge-skills]: https://skills.sh/b/fantasticmao/skills
[badge-license]: https://img.shields.io/badge/license-MIT-blue
[skills-sh]: https://skills.sh/fantasticmao/skills
[license]: LICENSE
[readme-zh]: README_ZH.md
[skill-readme-style]: skills/readme-style
[skills-cli]: https://github.com/vercel-labs/skills
