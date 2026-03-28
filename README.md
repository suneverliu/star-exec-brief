# star-brief

Codex skill for generating concise STAR project briefs from specs and recent code changes.

Codex 技能：基于 Spec 文档与最新代码变更，生成简明的 STAR 项目说明文档。

## Overview / 简介

This skill helps Codex read project specs and recent implementation changes, then produce a concise STAR project brief for non-technical readers. The output language follows the user's explicit instruction first, then the user's input language, and finally the main language of the spec when needed:

- Situation
- Task
- Action
- Result

这个 skill 会引导 Codex 读取项目规格文档与近期代码改动，并生成中文或英文的 STAR 项目说明文档。输出语言优先遵循用户明确指定，其次参考用户输入语言，必要时再参考 Spec 文档的主要语言，帮助非技术读者快速理解项目背景、目标、关键动作与结果。

## Install / 安装

Install this repository as a local Codex skill by placing the folder under your Codex `skills` directory.

将本仓库放到本地 Codex 的 `skills` 目录下即可安装。

Default location / 默认目录:

- If `CODEX_HOME` is set: `$CODEX_HOME/skills/star-brief`
- Otherwise: `~/.codex/skills/star-brief`

Windows examples:

- If `CODEX_HOME` is set: `$env:CODEX_HOME\skills\star-brief`
- Otherwise: `$env:USERPROFILE\.codex\skills\star-brief`

Clone with Git / 用 Git 安装:

```powershell
git clone https://github.com/aevost/star-brief.git "$env:USERPROFILE\.codex\skills\star-brief"
```

If you use `CODEX_HOME`:

```powershell
git clone https://github.com/aevost/star-brief.git "$env:CODEX_HOME\skills\star-brief"
```

Manual install / 手动安装:

1. Download this repository as a ZIP.
2. Extract it.
3. Ensure the folder name is `star-brief`.
4. Move it into your Codex `skills` directory.

1. 下载本仓库 ZIP。
2. 解压文件。
3. 确保目录名为 `star-brief`。
4. 将该目录放入 Codex 的 `skills` 目录。

## Usage / 使用方法

Invoke the skill explicitly:

```text
Use $star-brief to produce a concise, business-friendly STAR project brief from the workspace specs and latest code changes.
```

也可以直接使用中文描述任务，例如：

```text
请使用 $star-brief 读取当前工作区中的 Spec 文档和最新代码修改记录，生成一份简明的 STAR 项目说明文档。
```

## Notes / 说明

- The skill behavior is defined in `SKILL.md`.
- `agents/openai.yaml` provides UI metadata for Codex.
- `README.md` is for GitHub presentation and human readers only; it does not change the skill behavior.

- 这个 skill 的实际行为定义在 `SKILL.md` 中。
- `agents/openai.yaml` 用于 Codex 的界面元数据。
- `README.md` 仅用于 GitHub 展示和人工阅读，不会改变 skill 的触发或执行效果。

## License / 许可证

This project is released under the MIT License.

本项目使用 MIT License。
