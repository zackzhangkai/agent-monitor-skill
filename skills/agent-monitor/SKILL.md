---
name: agent-monitor
description: Inspect local Codex, Claude Code, and WorkBuddy sessions, agent processes and listening services on macOS; explain evidence-based activity states and generate an Obsidian-ready dashboard. Use when users need to see which agent projects or background services are active.
---

# Agent Monitor

Use the bundled Python detector to inspect local agent records and produce a project/session dashboard. Requires macOS, Python 3.9+, `/bin/ps` and `/usr/sbin/lsof`. No network service or Python packages are required.

## Inspect and report

1. Resolve this skill directory. Select an output directory dedicated to generated monitor data; use a user-provided vault when requested, otherwise a temporary directory. Preserve existing user notes.
2. Run `python3 <skill-dir>/scripts/monitor.py --vault <vault-or-temp-dir> --output-dir <dedicated-output-dir> --days 14`. Quote all paths. This scans once and writes `snapshot.json`, `自动监测.md` and `.monitor.lock`.
3. Read `snapshot.json`. Group sessions by `cwd`, list activity and attention states, then correlate agent processes and listening services by directory. Mention `checked_at` and any source errors. A failed or absent source is unavailable, not proof that no tasks exist.
4. Explain observed state and evidence together. Offer local session recovery only if requested; monitor output does not itself bind a desktop process to a session.

## Evidence rules

- A process being alive does not prove a task is executing.
- Recent tool activity is an inference, not a confirmed running state.
- A recorded turn completion means one response ended, not that the project passed acceptance.
- An old start without a completion is unconfirmed, not proof of a stuck task.
- WorkBuddy status comes from its database, not independent process verification.
- Counts of listening addresses are not counts of distinct services; one PID may bind multiple addresses.
- Do not stop monitored processes, alter agent databases, send prompts, or change agent configuration as part of inspection.

## Continuous refresh and Obsidian

The detector is one-shot. For a user-requested foreground refresh loop, run it every 30 seconds, wait for each scan to finish, and provide a way to stop the loop. Avoid creating a login service unless requested. For a persistent graphical Obsidian dashboard, point to the companion plugin: https://github.com/zackzhangkai/obsidian-agent-monitor . It refreshes while Obsidian is open and the plugin is enabled.

## Privacy and compatibility

Reads `~/.codex/state_5.sqlite` and referenced rollout tails, `~/.claude/projects/*/*.jsonl`, `~/.workbuddy/workbuddy.db`, process metadata and TCP listeners. SQLite is opened read-only; log reads are bounded. Never include real snapshots, private paths, chat titles or source transcripts in public examples. The parser follows current local database/event schemas; report schema errors instead of silently inventing support. Dashboard timestamps use Asia/Shanghai (UTC+8).

## Example requests

- “看看 Codex、Claude Code 和 WorkBuddy 哪些项目还在跑。”
- “生成一个 Obsidian 工作台，显示会话、进程和端口。”
- “这个任务是真的执行中，还是只有进程还活着？”
