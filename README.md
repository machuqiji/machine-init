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

## 适用范围：桌面端还是 CLI

现在的 AI 客户端分两种形态，各有各的适合场景：

**桌面端（WorkBuddy、OpenCode Desktop 等）**

- 面向所有人的形态。没接触过命令行的非开发者，直接用这个
- 交互友好——看图、截图、拖拽文件都是天然支持，对开发者来说体验也很好
- 缺点是能做的操作受客户端设计的限制

**CLI（pi、codex、opencode、claude code 等）**

- 开发者的形态。连接上你的大模型后基本开箱即用，不需要多少配置，但仍有一点使用成本——你得习惯终端里纯文本的交互方式
- 适合纯文本的工作：写代码、改配置、跑脚本
- 如果你的工作是图片、视频、多媒体类型的，不建议用 CLI——纯文本的交互肯定没有桌面端来得简单直接

选哪个归根结底是个人喜好，也可以都要：日常在桌面端聊天看东西，重活开 CLI。

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
