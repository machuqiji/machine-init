# machine-init

> 新机器 / 重装系统后，把 [init.md](init.md) 的内容整篇复制给带免费额度的桌面 AI（WorkBuddy、OpenCode Desktop 等），让它自动把开发环境装好。

## 为什么

我有四五台机器，经常折腾、重装。每次装环境都是重复劳动：装 git、装编辑器、装 code agent、配 git 身份……于是把这些固化成一份提示词。新机器到手只需要两步：

1. 装一个带免费大模型额度的桌面客户端（WorkBuddy / OpenCode Desktop）
2. 复制 `init.md` 全文，粘进对话框，说"按这个装"

模型会自己判断系统类型、选择安装方式、逐项验证，最后告诉你哪些东西需要手动登录。

## 用法

```text
1. 新机器装好 WorkBuddy 或 OpenCode Desktop（或任何能执行命令的 AI 客户端）
2. 打开 init.md，全选复制
3. 粘贴给模型，附一句你想装的 code agent（pi / codex / opencode / claude code）
4. 等它装完，按它最后给的清单手动完成登录类操作
```

进阶用法：在粘贴内容后面追加你的个性化要求（装某个 skill、配某个 MCP、装某个 CLI），模型会一并处理。

## 里面装什么

| 类别 | 内容 |
| --- | --- |
| 必装 | git、zed、node、bun、fd、ripgrep、jq、gh、glab、tmux、herdr、ssh |
| Agent 本体 | 用户点名哪个装哪个（pi / codex / opencode / claude code） |
| 常用 | pnpm、uv、fzf、docker |
| 可选 | yq、bat、eza、zoxide、starship、git-delta、lazygit |

清单哲学：只装真正用的，不装一堆"听起来很强"的 CLI。清单可增不可减——减了下次重装就少了。

## Fork 说明

`init.md` 里的 Git 身份是我的（machuqiji），fork 之后改成你自己的再粘贴。

## License

MIT
