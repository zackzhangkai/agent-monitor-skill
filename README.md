# Agent Monitor

**一句话，查看多个智能体的项目和运行状态。**

同时使用 Codex、Claude Code 和 WorkBuddy 时，让 Agent 帮你整理有活动的项目、需要关注的会话，以及仍在运行的后台服务。

**复制安装指令 → 发送给 Agent → 安装后粘贴使用指令。**

适用于 **macOS · Python 3.9+**。不需要 Obsidian，也不需要自己输入终端命令。

## 1. 复制安装指令

选择你使用的 Agent，复制对应整段文字发送给它，让它完成安装。无需自己在终端输入命令。

### Codex

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请阅读 skills/agent-monitor/SKILL.md，并把整个 Skill 目录（含配套脚本）安装到：
~/.codex/skills/agent-monitor

检查 Python 是否为 3.9 或以上版本。已有同名 Skill 时，请保留本地修改。
完成后告诉我是否安装成功，以及是否需要重启或开启新会话。
```

### Claude Code

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请阅读 skills/agent-monitor/SKILL.md，并把整个 Skill 目录（含配套脚本）安装到：
~/.claude/skills/agent-monitor

检查 Python 是否为 3.9 或以上版本。已有同名 Skill 时，请保留本地修改。
完成后告诉我是否安装成功，以及是否需要重启或开启新会话。
```

### WorkBuddy / 其他支持本地 Skill 的 Agent

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请先确认当前 Agent 的本地 Skill 安装方式和目录。
阅读 skills/agent-monitor/SKILL.md，把整个 Skill 目录（含配套脚本）安装到正确位置。
检查 Python 是否为 3.9 或以上版本。已有同名 Skill 时，请保留本地修改。
如果不支持安装本地 Skill，请说明，并尝试在当前会话中读取 SKILL.md、运行配套脚本。
完成后告诉我安装结果，以及下次如何调用。
```

WorkBuddy 的安装方式取决于当前版本；检测器可以读取其本地会话记录。安装完成后，按 Agent 的提示重新启动或开启新会话。

## 2. 粘贴这句话，开始使用

安装好后，把下面这句话粘贴到 Agent：

```text
使用 agent-monitor，检查最近 14 天 Codex、Claude Code 和 WorkBuddy 的项目，告诉我哪些有活动、哪些需要关注、哪些后台服务还在运行。
```

你会在对话中看到：

| 你想知道的事 | Agent 会整理的内容 |
| --- | --- |
| 哪些项目有活动？ | 最近会话、记录时间和匹配进程 |
| 哪些任务需要关注？ | 异常、中断、终止及状态未确认的会话 |
| 哪些后台服务还开着？ | 服务进程、监听端口和工作目录 |

每次调用检测一次。它只读取本机记录，不修改会话、不停止进程。**进程存活不等于任务正在执行；一轮响应结束不等于项目已验收。**

## 联系与交流

- 个人微信：`zack6116`
- X：[@kaiz_amm](https://x.com/kaiz_amm)

### 个人微信

![个人微信二维码](images/wechat-contact.png)

### AI 学习交流圈

![微信交流群二维码](images/wechat-community.jpg)

当前交流群二维码有效期截至 **2026-10-07**；失效后可添加个人微信索取新二维码。飞书群尚未建立，入口待补充。

## License

[MIT](LICENSE)。独立社区项目，与 OpenAI、Anthropic、腾讯及 Obsidian 无隶属关系。

## 想在 Obsidian 里持续查看？

打开 **Obsidian → 设置 → 第三方插件 → 浏览**，搜索 **Agent Monitor**，安装并启用即可使用图形工作台。Obsidian 打开且插件启用时会自动刷新。

- [Obsidian 官方社区插件目录](https://obsidian.md/plugins)
- [Agent Monitor 插件 GitHub 仓库](https://github.com/zackzhangkai/obsidian-agent-monitor)
