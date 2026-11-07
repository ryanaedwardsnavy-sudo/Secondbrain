---
title: LLM wiki operations
tags: [method, llm, knowledge-management, workflow]
created: 2026-11-07
updated: 2026-11-07
---

# LLM wiki operations

**One-line summary:** The [[llm-wiki-pattern]] runs on three operations: ingest a source, query the wiki, and lint it for rot.

## Key points

- **Ingest:** a new source gets a summary page, and the LLM updates every related page, link, and contradiction flag. One source can touch many pages.
  - In the article's demo, the second ingest updated existing pages and added a cross-link the author never wrote.
- **Query:** questions are answered from the wiki's synthesized pages, not the raw files.
  - A good answer can be filed back into the wiki as a new page, so the wiki gets smarter from use, not just from new sources.
- **Lint:** periodic audits for three problems:
  - contradictions between pages,
  - orphan pages with no inbound links, and
  - concepts that are mentioned but have no page of their own.
- **Setup step:** the walkthrough has the agent interview you first (topic, source types, expected volume, and page types) before it writes the schema, `wiki/index.md`, and `wiki/log.md`.

## How I'd use this

- Ingest maps to `/ingest`, and query maps to the GitHub `ask` flow. Compiled answers go to `output/` today rather than back into `wiki/`.
- Lint has no equivalent here yet. A `/lint` skill could check for orphans, unresolved `[[wikilinks]]`, notes over 400 words, and missing `## Sources`.
- A `wiki/log.md` would give a running record of what each ingest touched.

## Related

- [[llm-wiki-pattern]]
- [[llm-wiki-vs-rag]]

## Sources

- `raw/articles/2026-11-07-karpathy-llm-wiki.md`

## Open questions

- In this repo, should good query answers be filed into `wiki/`, `output/`, or both?
