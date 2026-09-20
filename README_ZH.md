# FantasticMao 的 skills 集

[![skills.sh](https://skills.sh/b/fantasticmao/skills)](https://skills.sh/fantasticmao/skills)
[![license](https://img.shields.io/github/license/fantasticmao/skills)](LICENSE)

README [English](README.md) | [中文](README_ZH.md)

## 这是什么

FantasticMao 的 skills 集提供定制开发的 agent skills。每个 skill 都是一份 `SKILL.md` 文档，说明某类重复出现的任务应当如何完成，支持 skill 的编码 agent 会按需加载。其中仅含指令，不含可执行工具、依赖或 MCP server。

## 特性

- **[readme-style](skills/readme-style)** — 以统一的语体、结构与格式撰写并改写 README，双语版本亦在其列。

## 下载与安装

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

agent 会将请求与已安装的每个 skill 的 `description` 相匹配，并应用命中的那一个。点明 skill 名称即可显式指定：

```text
使用 readme-style skill 改写本项目的 README。
```

## 许可证

FantasticMao 的 skills 集以 [MIT License](LICENSE) 发布。
