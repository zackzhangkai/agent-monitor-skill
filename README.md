# Agent Monitor Skill · 多智能体任务监测

Codex、Claude Code、WorkBuddy 同时开了很多项目，不知道哪些还在跑？把下面的安装指令复制到你使用的 Agent，安装后用一句话查看项目、会话和后台服务。

目前检测功能支持 **macOS**，需要 **Python 3.9+**。

## 第一部分：安装

选择你使用的 Agent，复制对应整段文字发送给它，让它完成安装。无需自己在终端输入命令。

### Codex

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请读取仓库里的 skills/agent-monitor/SKILL.md，将整个 skills/agent-monitor 目录安装到 ~/.codex/skills/agent-monitor，保留 scripts 等配套文件。检查当前 Mac 是否有 Python 3.9 或以上版本；如果已有同名 Skill，请先检查本地修改，不要直接覆盖。完成后告诉我安装结果，以及是否需要重新启动或开启新会话。
```

### Claude Code

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请读取仓库里的 skills/agent-monitor/SKILL.md，将整个 skills/agent-monitor 目录安装到 ~/.claude/skills/agent-monitor，保留 scripts 等配套文件。检查当前 Mac 是否有 Python 3.9 或以上版本；如果已有同名 Skill，请先检查本地修改，不要直接覆盖。完成后告诉我安装结果，以及是否需要重新启动或开启新会话。
```

### WorkBuddy / 其他支持本地 Skill 的 Agent

```text
请帮我安装 agent-monitor Skill，仓库地址：
https://github.com/zackzhangkai/agent-monitor-skill

请先确认当前工具支持的本地 Skill 安装方式和目录，再读取仓库里的 skills/agent-monitor/SKILL.md，将整个 skills/agent-monitor 目录安装到正确位置，保留 scripts 等配套文件。不要套用 Codex 或 Claude Code 的安装目录。检查当前 Mac 是否有 Python 3.9 或以上版本；如果已有同名 Skill，请先检查本地修改，不要直接覆盖。如果当前工具不支持安装本地 Skill，请明确说明，并告诉我如何在当前会话中读取 SKILL.md 和运行配套检测脚本。完成后告诉我安装结果。
```

WorkBuddy 的安装方式取决于当前版本；检测器可以读取其本地会话记录。安装完成后，按 Agent 的提示重新启动或开启新会话。

## 第二部分：使用

安装好后，把下面这句话粘贴到 Agent：

```text
使用 agent-monitor，检查最近 14 天 Codex、Claude Code 和 WorkBuddy 的项目，告诉我哪些有活动、哪些需要关注、哪些后台服务还在运行。请按项目整理结果，注明检测时间，并区分“任务有执行证据”“进程仍存活”和“状态未确认”。
```

每次调用检测一次，结果直接显示在对话里。它会读取本机会话记录、进程和监听端口，不修改原有会话，也不会停止任何进程。进程存活不代表任务正在执行，一轮响应结束也不代表项目已验收。

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
