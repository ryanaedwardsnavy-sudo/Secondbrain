---
title: LLM wiki pattern
tags: [method, llm, knowledge-management, karpathy]
created: 2026-11-07
updated: 2026-11-07
---

# LLM wiki pattern

**One-line summary:** Andrej Karpathy's method for a personal knowledge base: an LLM compiles raw sources into a linked markdown wiki once and keeps it current, so questions are answered from the wiki rather than by re-reading sources.

## Key points

- **Origin:** Karpathy tweeted the idea on 2026-04-02, then posted a gist, `llm-wiki.md`. He calls it an "idea file": you paste it into an agent like Claude Code and the agent builds the setup.
- **Compile, don't retrieve:** raw sources work like source code and the wiki like the compiled binary. The synthesis happens once at ingest, not again on every question.
- **Three layers:**
  1. Raw sources: immutable, read but never edited, so the wiki can always be rebuilt.
  2. The wiki: markdown pages the LLM owns (concepts, entities, summaries, an index, and a log).
  3. The schema: a CLAUDE.md or AGENTS.md that sets conventions and the ingest and query rules.
- **Division of labor:** the human curates sources and asks questions. The LLM summarizes, cross-links, files, and flags contradictions.
- **Three operations:** ingest, query, and lint. See [[llm-wiki-operations]].
- **Why it works now:** personal wikis usually die because upkeep costs more than they return. An LLM carries the upkeep. The article ties this to Vannevar Bush's 1945 Memex idea.
- **Tooling in the walkthrough:** Claude Code or Codex as the agent, Obsidian as the viewer (graph view shows pages as nodes and links as edges), and a plain local folder as the vault.

## How I'd use this

- It's the design basis for this second brain; useful when deciding how to evolve the vault.
- This repo already maps onto it: `raw/` is layer 1, `wiki/` is layer 2, `CLAUDE.md` is layer 3, and `output/` adds a deliverables stage on top.
- The earlier gaps against the pattern are now closed: `wiki/log.md`, a `/lint` skill, and a rule for filing good answers back into the wiki. See [[llm-wiki-operations]].

## Related

- [[llm-wiki-operations]]
- [[llm-wiki-vs-rag]]
- [[second-brain-method]]
- [[anthropic-repos]]

## Sources

- `raw/articles/2026-11-07-karpathy-llm-wiki.md`

## Open questions

- The article summarizes Karpathy's gist; the gist itself isn't captured in `raw/` yet.
