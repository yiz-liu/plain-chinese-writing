# 简明中文写作

`plain-chinese-writing` 用于起草、改写、润色和审阅文档，让读者快速找到重点并理解内容，整体设计理念来自于 ISO 24495 标准。

## 适用场景

- 起草通知、邮件、说明文档等实用文本。
- 整理会议纪要和报告，突出结论、条件与后续行动。
- 改写冗长、生硬或空泛的文字，处理公文腔、翻译腔和AI腔。
- 审阅现有文本，指出理解障碍并给出具体修改建议。

## 安装方法

先安装 Node.js 22.20 或更高版本，再通过 [skills 安装器](https://github.com/vercel-labs/skills) 从本仓库安装。以下命令安装到用户目录，可在各个项目中使用。

### Codex CLI 与 DeepSeek Harness（DSH）

```sh
npx skills add yiz-liu/plain-chinese-writing --agent codex --global
```

这条命令将技能安装到 `~/.agents/skills/plain-chinese-writing/`。Codex CLI 和默认配置下的 DSH 都会读取这个目录，因此安装一次即可共用。`--agent codex` 用于选择安装位置，使用 DSH 时也可执行同一条命令。

### Claude Code

```sh
npx skills add yiz-liu/plain-chinese-writing --agent claude-code --global
```

安装器会在 Claude Code 的用户技能目录中建立入口，默认位置为 `~/.claude/skills/plain-chinese-writing/`。

同时使用上述工具时，可以一次安装：

```sh
npx skills add yiz-liu/plain-chinese-writing --agent codex claude-code --global
```

### 项目安装与本地安装

仅在当前项目中使用时，在项目根目录执行上述命令并去掉 `--global`。Codex CLI 和 DSH 使用 `.agents/skills/`，Claude Code 使用 `.claude/skills/`。

已经下载源码时，也可把命令中的仓库地址替换为本地目录。例如，在包含 `SKILL.md` 的目录中执行：

```sh
npx skills add . --agent codex claude-code --global
```

手动安装时，将 `SKILL.md`、`references/`、`agents/`、`README.md` 和 `LICENSE` 放入所用工具的用户技能目录：

| 工具 | 默认用户技能目录 |
| --- | --- |
| Codex CLI | `~/.agents/skills/plain-chinese-writing/` |
| Claude Code | `~/.claude/skills/plain-chinese-writing/` |
| DSH | `~/.dsh/skills/plain-chinese-writing/`，也支持 `~/.agents/skills/plain-chinese-writing/` |

完成后启动工具，在技能列表中确认出现 `plain-chinese-writing`。其他工具可通过 `npx skills add yiz-liu/plain-chinese-writing --global` 交互选择，或将技能文件放入其指定目录。

## 文件说明

- [技能说明](SKILL.md)：适用范围、写作流程和交付前检查。
- [写作指南](references/zh-hans-guide.md)：中文表达、专业文本、标点与数字的具体处理方法。
- [改写示例](references/examples.md)：原文、改文和修改理由。
- [调用配置](agents/openai.yaml)：显示名称、简介和默认调用提示。

## 许可证

本技能采用 [MIT 许可证](LICENSE)，允许使用、修改和分发。分发副本或实质性内容时须保留版权声明和许可声明，具体条款以许可证全文为准。
