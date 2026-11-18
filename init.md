# 新机器初始化

你要帮我初始化一台新装好的开发机。下面是我的软件清单和规则，你来判断装法、版本和验证方式。目标只有一个：清单里的软件装好、能用。

## 开始前

1. 先探测系统：macOS（brew）、Ubuntu/Debian（apt）、Windows（winget）。Windows 上额外装 OpenSSH Server。
2. 如果缺少包管理器（如 brew），先装包管理器再继续。
3. 每装完一个软件，用它的验证命令确认能执行（如 `--version`），再装下一个。
4. 装不上的不要跳过装下一个就完事——换安装方式重试（官方安装脚本、直接下载二进制等），实在不行最后在报告里说明。

## Git 身份（必须配置，装完 git 立刻做）

```bash
git config --global user.name "machuqiji"
git config --global user.email "machuqiji@163.com"
```

配置完回读 `git config --global --list` 确认生效。如果之前有别的值，直接覆盖。

## 必装

- git — 版本控制
- zed — 默认文本编辑器（看 md、改配置），重活再开 IDE；装完关掉遥测上报和 AI 助手，纯当编辑器用
- node — JS 运行时
- bun — pi 等基于 bun 的 agent 的运行时，也是日常跑脚本的首选
- fd — 找文件
- ripgrep — 搜内容
- jq — 看 JSON
- gh — GitHub CLI
- glab — GitLab CLI
- tmux — 长任务、dev server 挂后台（Windows 上可用等价方案或跳过）
- herdr — 多 agent 面板
- ssh — 客户端和 server 都装（Windows 也额外装 OpenSSH Server）

## Agent 本体

我会在对话里点名装哪个，装我点名的那个：

- pi
- codex
- opencode
- claude code

没点名就问我，不要自作主张全装。

## 常用

- pnpm — 前端项目
- uv — Python 项目
- fzf — 模糊选择
- docker — 容器

## 可选

- yq — 看 YAML
- bat / eza — 带颜色的 cat / ls
- zoxide — 智能 cd
- starship — shell 提示符
- git-delta / lazygit — diff 和 git TUI

## 不装

- 语言运行时版本管理器（nvm/fnm/asdf）——需要时再说
- 一堆用不上的 CLI 工具——清单只增不减会变成垃圾堆

## 装完之后

输出一份报告，包含三部分：

1. **已装清单**：软件名 + 版本号 + 验证结果
2. **失败项**：哪个没装上、试了什么、建议怎么办
3. **需要我手动做的**：登录类操作模型做不了，列出来，比如：
   - `gh auth login` 走浏览器 OAuth
   - `glab auth login`
   - 各种软件的账号登录
   - ssh key 生成后要到各个平台添加公钥

如果发现我在这台机器上还需要装 skill（`npx skills add <name>`）、MCP 服务、或某个 CLI 工具，而清单里没有，先问我再装。
