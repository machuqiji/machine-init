# os-init-skill

> 新机器 / 重装系统后，让 AI 把开发环境装好。装成 skill，对 agent 说"初始化这台机器"，它会自动判断系统、装软件、逐项验证。

## 用法

机器上已经装好任意 code agent（WorkBuddy / OpenCode Desktop / pi / codex 等）时：

```bash
npx skills add machuqiji/os-init-skill
```

装好后对 agent 说"初始化这台机器"或"装开发环境"，skill 会自动触发。

全新机器上还没有 agent？先手动装一个带免费大模型额度的客户端（WorkBuddy / OpenCode Desktop 等），然后同上——桌面客户端也在这个 skill 的必装清单里，装完 agent 后把它装成 skill，下次重装就只需要这一步了。

## 为什么

我有四五台机器，经常折腾、重装。每次装环境都是重复劳动：装 git、装编辑器、装客户端、装 code agent……于是把这些固化下来。新机器到手只需要两步：

1. 装一个能执行命令的 AI 客户端（桌面端或 CLI 都行）
2. 装上这个 skill，说"按这个装"

模型会自己判断系统类型（macOS / Ubuntu / Windows）、选择安装方式、逐项验证，最后告诉你哪些东西需要手动登录。

## 里面装什么

| 类别 | 内容 |
| --- | --- |
| 必装 | WorkBuddy、OpenCode Desktop、豆包、git、zed、node、gh、herdr 桌面版、ssh |
| Agent 本体 | 用户点名哪个装哪个（pi / codex / opencode / claude code） |

清单哲学：只装真正用的，不装一堆"听起来很强"的 CLI。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `SKILL.md` | skill 本体，装到 agent 后自动触发 |

## License

MIT
