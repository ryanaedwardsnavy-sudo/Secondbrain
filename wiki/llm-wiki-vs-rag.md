---
title: LLM wiki vs RAG
tags: [llm, rag, knowledge-management, tradeoffs]
created: 2026-11-07
updated: 2026-11-07
---

# LLM wiki vs RAG

**One-line summary:** RAG fits big, changing corpora that need exact citations. An [[llm-wiki-pattern]] fits small, curated collections where synthesis across sources matters most.

## Key points

- **Neither wins outright.** The article frames them as tools for different problems.
- **RAG fits** large, frequently changing corpora where answers need precise citations back to the source.
- **An LLM wiki fits** smaller, curated sets (the article suggests roughly 100 to 500 sources) where connecting ideas across sources is the point.
- **LLM wiki costs and risks:**
  - Ingest is expensive, since one source can rewrite many pages.
  - Answers sit one or two steps removed from the raw source.
  - Updating a source means re-ingesting it.
  - A summary error can harden into a "fact" and spread through linked pages.
- **Mitigation:** run regular lint passes (see [[llm-wiki-operations]]) and spot-check wiki pages against their raw sources.

## How I'd use this

- This vault is a small, curated collection, so the wiki approach fits.
- The "every claim has a source" rule is the guard against error spread: each note's `## Sources` gives a spot-check path back to `raw/`.

## Related

- [[llm-wiki-pattern]]
- [[llm-wiki-operations]]
- [[anthropic-repos]]

## Sources

- `raw/articles/2026-11-07-karpathy-llm-wiki.md`

## Open questions

- The 100 to 500 source range is the article author's estimate, not a tested limit.
