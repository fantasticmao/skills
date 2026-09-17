# Skills

[![skills.sh][badge-skills]][skills-sh] [![license][badge-license]][license]

[English][readme-en] | 简体中文

## 这是什么

本仓库收录 FantasticMao 在日常开发中使用的 agent skills。每个 skill 都是一份 `SKILL.md` 文档，说明某类重复出现的任务应当如何完成，支持 skill 的编码 agent 会按需加载。本仓库仅提供指令，不含可执行工具、依赖或 MCP server。

## Skills

- **[readme-style][skill-readme-style]** — 以统一的语体、结构与格式撰写并改写 README，双语版本亦在其列。

## 安装

```bash
npx skills add fantasticmao/skills
```

```bash
# 安装到当前用户的所有项目
npx skills add fantasticmao/skills -g

# 仅安装单个 skill
npx skills add fantasticmao/skills -s readme-style

# 列出可用的 skill 而不安装
npx skills add fantasticmao/skills -l
```

> [!NOTE]
> 该命令默认安装到当前项目，`-g` 则改为安装到用户目录。`-a` 用于限定目标 agent，`npx skills update` 用于获取后续修订。

## 快速开始

agent 会将请求与已安装的每个 skill 的 `description` 相匹配，并自行应用命中的那一个。点明 skill 名称即可显式指定：

```text
使用 readme-style skill 改写本项目的 README。
```

## 工作原理

每个 skill 以独立目录置于 `skills/` 之下，其中的 `SKILL.md` 在 YAML frontmatter 里声明 `name` 与 `description`。该扁平布局正是 [skills CLI][skills-cli] 的发现路径之一，因此安装过程会将目录复制到所选各 agent 的 skills 路径。frontmatter 常驻于 agent 上下文，正文只在请求命中描述之后读取，闲置的 skill 因此开销很低。

[badge-skills]: https://skills.sh/b/fantasticmao/skills
[badge-license]: https://img.shields.io/badge/license-MIT-blue
[skills-sh]: https://skills.sh/fantasticmao/skills
[license]: LICENSE
[readme-en]: README.md
[skill-readme-style]: skills/readme-style
[skills-cli]: https://github.com/vercel-labs/skills
