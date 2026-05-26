# Work Review

Work Review is a portable prompt and Codex skill for reviewing recent vibe coding or AI-assisted work, finding repeated manual workflows, learning practical work habits, and deciding what should become a reusable prompt, skill, slash command, playbook, custom agent, automation, or personalization rule.

It is designed to work across tools such as Codex, Claude Code, WorkBuddy, Cursor, GitHub, local repositories, notes, tickets, and exported chats.

## What It Does

Work Review helps an AI assistant:

- Look back over the last 30 days of available work history, or all available history if shorter.
- Identify repeated, time-consuming, error-prone, or context-heavy workflows.
- Use evidence rather than guesses.
- Check whether existing reusable assets already cover the workflow.
- Recommend the smallest useful form: prompt, skill, slash command, playbook, agent, automation, extend existing, or skip.
- Infer practical preferences that help future AI assistants match the user's habits, communication style, quality bar, and toolchain.
- Create only high-confidence missing assets when asked.

## Quick Start

### Codex

Install this repository as a Codex skill by placing it under your Codex skills directory as `work-review`, then invoke:

```text
Use $work-review to review my recent vibe coding work across available tools and identify high-confidence reusable workflows to package.
```

### Claude Code, WorkBuddy, Cursor, or Other Tools

Use the portable prompt in [`references/portable-prompt.md`](references/portable-prompt.md). You can paste it into:

- a Claude Code slash command
- a WorkBuddy playbook or agent prompt
- a Cursor rule or reusable prompt
- a custom agent instruction
- any AI assistant that can inspect recent work artifacts

## Output Shape

The assistant first produces a compact shortlist:

| Repeated workflow | Evidence and dates | Frequency / confidence | Recommended form | Why / why not |
|---|---|---:|---|---|

It also produces a practical personalization profile:

| Habit / preference | Evidence and dates | Confidence | Future adaptation | Memory candidate |
|---|---|---:|---|---|

Then it reports:

- what should be created or extended now
- what personalization guidance should be used in future work
- what should be deliberately skipped
- what needs more evidence before packaging or personalization

## Files

- [`SKILL.md`](SKILL.md): Codex skill definition and platform-neutral workflow.
- [`references/portable-prompt.md`](references/portable-prompt.md): Cross-tool prompt body.
- [`references/report-template.md`](references/report-template.md): Suggested report format.
- [`agents/openai.yaml`](agents/openai.yaml): Codex UI metadata.

## Principles

- Evidence first.
- Smallest useful reusable asset.
- Reuse or extend before duplicating.
- Personalize future help from evidence, not guesses.
- Skip speculative or overly broad packaging.
- Keep outputs narrow, practical, source-aware, and easy to validate.

## License

MIT
