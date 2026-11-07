---
title: Anthropic repos
tags: [claude, tooling, github]
created: 2026-11-06
updated: 2026-11-06
---

# Anthropic repos

**One-line summary:** Five official Anthropic repos covering skill authoring, @claude in GitHub, PR security scanning, the Python Agent SDK, and example notebooks.

## Key points

- **skills** ([github.com/anthropics/skills](https://github.com/anthropics/skills)): reference examples of how a SKILL.md package is structured.
- **claude-code-action** ([github.com/anthropics/claude-code-action](https://github.com/anthropics/claude-code-action)): mention @claude on an issue or PR and it responds or pushes a fix to a branch. Wired into this repo.
- **claude-code-security-review** ([github.com/anthropics/claude-code-security-review](https://github.com/anthropics/claude-code-security-review)): runs Claude over PR diffs looking for vulnerabilities. Useful on code repos, not much use on a notes vault.
- **claude-agent-sdk-python** ([github.com/anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python)): drive Claude Code from Python with custom tools and hooks.
- **claude-cookbooks** ([github.com/anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks)): notebooks for RAG, tool use, classification, and structured output.

## How I'd use this

- Skills repo as the pattern for `.claude/skills/` here.
- Agent SDK for anything that needs to run agents outside of chat.

## Related

- [[second-brain-method]]

## Sources

- X post by @rvaniaaaa, 2026-11-06 (screenshot, not archived)

## Open questions

- The post's dashboard graphic is promotional, not a real tool.
