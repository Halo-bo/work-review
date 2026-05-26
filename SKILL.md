---
name: work-review
description: Review recent vibe coding or AI-assisted work history across Codex, Claude Code, WorkBuddy, Cursor, GitHub, local repositories, notes, or other available tools to identify repeated manual workflows worth packaging into reusable prompts, skills, slash commands, custom agents, playbooks, or automations. Use when the user asks to audit recent work, mine coding-agent sessions for repeatable patterns, create a shortlist of reusable workflows, decide whether to build a skill/agent/automation/playbook, or perform a past-work retrospective for software, research, writing, operations, planning, or personal administration tasks.
---

# Work Review

## Goal

Turn recent AI-assisted work history from any accessible vibe coding environment into a compact, evidence-based shortlist of repeated workflows, then create only the high-confidence missing assets requested or clearly implied by the user.

Prefer the smallest portable form that fits the user's toolchain: a narrow skill, slash command, reusable prompt, playbook, or template when the work is a repeatable procedure; a custom agent/subagent when the work is a bounded specialist role or investigation; an automation when the work is a scheduled check, report, reminder, or monitor.

## Evidence Order

Use available evidence in this order:

1. Current tool history and artifacts available to the agent: Codex sessions, Claude Code transcripts, WorkBuddy logs, Cursor chats, task summaries, repo history, issue/PR context, or files the user provides.
2. Persistent memories, rollout summaries, notes, local knowledge bases, project journals, or prior conversation summaries available in the environment.
3. Source-system evidence such as Git commits, branches, PRs, issues, tickets, docs, calendars, chat exports, browser history, or activity logs when explicitly available or enabled. Use secondary logs for discovery, then confirm important facts in the source system when possible.
4. Existing reusable assets in the user's toolchain: Codex skills, Claude Code commands, WorkBuddy playbooks, custom agents, plugins, scripts, templates, and automations, so the recommendation extends or reuses what exists before creating duplicates.

Do not invent history. If a platform-specific history source is unavailable, say so and produce a smaller shortlist from the artifacts that can actually be inspected. Never require Codex-only evidence when another tool's logs or project artifacts are the best available source.

## Discovery Workflow

1. Define the lookback window. Default to the last 30 days, or all available history if shorter. Respect any window the user provides.
2. Inventory candidate work across coding, debugging, design, research, writing, planning, communication, operations, analysis, and personal administration.
3. Cluster similar tasks by stable inputs, repeated steps, decision points, and expected output.
4. Check whether each cluster is already covered by an existing skill, slash command, prompt, agent, automation, script, template, playbook, or documented process in the relevant tool.
5. Score each candidate using the gate below.
6. Produce the shortlist before creating anything.
7. Create or extend only high-confidence missing items, unless the user asks for analysis only.

## Packaging Gate

Only act on a candidate when it satisfies all of these:

- Occurred at least twice, or is clearly likely to recur and costly to repeat.
- Has stable inputs, a repeatable procedure, and a clear output or stopping condition.
- Would materially improve speed, quality, consistency, or reliability.
- Is not already adequately covered.
- Is not too sensitive, speculative, ambiguous, broad, or dependent on unavailable private context.

Use "needs more evidence" for promising but under-supported candidates. Use "skip" for work that is one-off, fuzzy, risky, or already handled well enough.

## Output Format

First produce a compact shortlist. Use this table when possible:

| Repeated workflow | Evidence and dates | Frequency / confidence | Recommended form | Why / why not |
|---|---|---:|---|---|

Then give a decision:

- **Create or extend now**: high-confidence missing items in the user's target toolchain.
- **Deliberately skip**: candidates that fail the gate.
- **Needs more evidence**: candidates to revisit after more examples.

When the user wants implementation, continue from the shortlist into the relevant creation workflow for the target tool. Keep created assets narrow, practical, source-aware, and easy to validate.

## Creation Guidance

For reusable prompts, playbooks, slash commands, or skills:

- Use the host tool's native packaging format when it is known and available. Examples: Codex skill, Claude Code slash command or `CLAUDE.md` workflow, WorkBuddy playbook/agent prompt, Cursor rule/prompt, or a portable Markdown prompt if no native packaging format is available.
- Put the workflow, trigger context, evidence rules, stopping conditions, and output expectations in the native file or prompt.
- Add references only when they reduce repeated context loading.
- Validate with the host tool's validator or a dry-run invocation when possible.

For custom agents or subagents:

- Define the bounded role, inputs, source systems, allowed tools, decision criteria, and final report shape.
- Avoid broad "do everything" agents. Create an agent only when delegation to a specialist role is clearer than a reusable playbook.

For automations:

- Use the automation tool when available.
- Make the prompt self-contained.
- Include the exact schedule, destination, expected output, and stopping or escalation conditions.
- Prefer a paused or suggested automation when the source systems, permissions, or cadence are uncertain.

If the target tool is unclear, ask one concise question about the intended toolchain before creating files. If the user wants cross-tool reuse, create a portable Markdown prompt/playbook first and optionally add thin adapters for each platform.

## Validation

Before finishing:

- Verify created or changed files exist and are valid for the host system.
- Check for overlap with existing assets one more time.
- Report what was created or extended, what was skipped, and what needs more evidence.
- If the user's language is not English, answer the retrospective in the user's language unless they ask otherwise.

## Reference

For a reusable shortlist and report skeleton, read `references/report-template.md` when preparing the final retrospective.

For tools that cannot consume Codex skills directly, use `references/portable-prompt.md` as the cross-tool prompt body for a Claude Code slash command, WorkBuddy playbook, Cursor prompt/rule, custom agent instruction, or shared Markdown workflow.
