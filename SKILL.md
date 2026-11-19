---
name: os-init
description: 新机器/重装系统后的开发环境初始化。
---

# os-init — 新机器初始化

帮用户初始化一台新装好的开发机。下面是软件清单和规则，由你判断装法、版本和验证方式。目标只有一个：清单里的软件装好、能用。

## 开始前

1. 先探测系统：macOS（brew）、Ubuntu/Debian（apt）、Windows（winget）。Windows 上额外装 OpenSSH Server。
2. 如果缺少包管理器（如 brew），先装包管理器再继续。
3. **幂等**：每个软件安装前先跑验证命令（如 `--version`），已装且能通过的直接跳过，不要重装或升级。
4. 每装完一个软件，用它的验证命令确认能执行，再装下一个。
5. 装不上的不要跳过装下一个就完事——换安装方式重试（官方安装脚本、直接下载二进制等），实在不行最后在报告里说明。

## 必装
- workbuddy
- opencode desktop
- 豆包
- git — 版本控制
- zed — 默认文本编辑器（看 md、改配置），重活再开 IDE；装完写配置关掉遥测和 AI 助手（见下），纯当编辑器用
- node — JS 运行时
- gh — GitHub CLI
- herdr 桌面版 — 多 agent 面板
- ssh — 客户端和 server 都装

### zed 配置（装完立刻写）

写入 `~/.config/zed/settings.json`（已存在则合并，不覆盖用户已有的其他字段）：

```json
{
  "telemetry": { "metrics": false, "diagnostics": false },
  "features": { "edit_prediction_provider": "none" }
}
```

## Agent 本体（pi / codex / opencode / claude code）

装用户点名的那个。用户没点名就先问，不要自作主张全装。

## 装完之后

输出一份 markdown 报告，包含三部分：

1. **已装清单**（表格）：软件名 | 版本号 | 验证结果
2. **失败项**：哪个没装上、试了什么、建议怎么办
3. **需要手动做的**：登录类操作模型做不了，列出来，比如：
   - `gh auth login` 走浏览器 OAuth
   - 各种软件的账号登录
   - ssh key 生成后要到各个平台添加公钥
