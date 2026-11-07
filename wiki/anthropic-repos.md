---
title: Anthropic repos
tags: [claude, tooling, github]
created: 2026-11-06
updated: 2026-11-07
---

# Anthropic repos

**One-line summary:** Five official Anthropic repos covering skill authoring, @claude in GitHub, PR security scanning, the Python Agent SDK, and example notebooks.

## Key points

- The post's argument: people hand-build things Anthropic has already open-sourced. Pick one repo and add it to your own.
- **skills** ([github.com/anthropics/skills](https://github.com/anthropics/skills)): reference examples of how a SKILL.md package is structured.
- **claude-code-action** ([github.com/anthropics/claude-code-action](https://github.com/anthropics/claude-code-action)): mention @claude on an issue or PR and it responds or pushes a fix to a new branch, with signed commits. Wired into this repo.
- **claude-code-security-review** ([github.com/anthropics/claude-code-security-review](https://github.com/anthropics/claude-code-security-review)): runs Claude over PR diffs looking for vulnerabilities and filters out noisy findings. Useful on code repos, not much use on a notes vault.
- **claude-agent-sdk-python** ([github.com/anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python)): drive Claude Code from your own Python app with custom tools and hooks.
- **claude-cookbooks** ([github.com/anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks)): runnable notebooks for RAG, tool use, classification, and structured output.
- The post's graphic quotes @imryven's "How to Build a Second Brain With Claude and Obsidian" (2026-10-27): a raw/ → wiki/ → output/ folder run by a CLAUDE.md. That's the layout this repo copies.

## How I'd use this

- This is the post that started this repo.
- Skills repo as the pattern for `.claude/skills/` here.
- Agent SDK for anything that needs to run agents outside of chat.

## Related

- [[second-brain-method]]

## Sources

- `raw/threads/2026-11-07-rvaniaaaa-anthropic-repos.md` (X post by @rvaniaaaa, 2026-11-06; paraphrased from screenshots)

## Open questions

- The post's dashboard graphic is promotional, not a real tool.
- The raw capture is a paraphrase, not the verbatim post. Swap in the original text if it becomes available.
