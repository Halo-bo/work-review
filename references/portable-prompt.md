# Portable Prompt: Work Review

Use this prompt in any AI coding or work assistant that can access recent work history, project files, commits, tickets, notes, or chat/task exports.

```text
Look back over my recent vibe coding or AI-assisted work from the last 30 days, or all available history if shorter, and identify repeated manual workflows worth packaging.

Use available evidence in this order:
- Current tool history and artifacts available to you, such as Codex sessions, Claude Code transcripts, WorkBuddy logs, Cursor chats, task summaries, repo history, issue/PR context, or files I provide.
- Persistent memories, rollout summaries, notes, local knowledge bases, project journals, or prior conversation summaries available in the environment.
- Source-system evidence such as Git commits, branches, PRs, issues, tickets, docs, calendars, chat exports, browser history, or activity logs when explicitly available or enabled. Use secondary logs for discovery only; confirm important details in the source system when possible.
- Existing reusable assets in my toolchain, such as skills, slash commands, playbooks, custom agents, plugins, scripts, templates, and automations, so you reuse or extend what already exists instead of duplicating it.

Look broadly for work that is repeated, time-consuming, error-prone, context-heavy, or benefits from a consistent process. Include workflows across coding, debugging, research, writing, planning, communication, operations, analysis, and personal administration.

Only act on a candidate when it:
- occurred at least twice, or is clearly likely to recur and costly to repeat;
- has stable inputs, a repeatable procedure, and a clear output or stopping condition;
- would materially improve speed, quality, consistency, or reliability;
- is not already adequately covered;
- is not too sensitive, speculative, ambiguous, broad, or dependent on unavailable private context.

Choose the smallest appropriate form:
- Reusable prompt / playbook / skill / slash command: a repeatable workflow or procedure.
- Custom agent / subagent: a bounded specialist role or investigation task suitable for delegation.
- Automation: a scheduled or recurring check, report, reminder, or monitor.
- Skip: work that is too one-off, ambiguous, sensitive, already covered, or poorly evidenced to package.

First produce a compact shortlist with:
- repeated workflow
- supporting evidence and dates
- frequency / confidence
- recommended form: prompt, skill, slash command, playbook, agent, automation, extend existing, or skip
- why it is or is not worth creating

Then create only the high-confidence missing items I ask for or that are clearly implied by the request. Keep them narrow, practical, source-aware, and easy to validate. If the target tool is unclear, ask one concise question before creating files. If I want cross-tool reuse, create a portable Markdown prompt/playbook first and optionally add thin adapters for each platform.

Finish with:
- what you created or extended
- what you deliberately skipped
- what needs more evidence before packaging
```
