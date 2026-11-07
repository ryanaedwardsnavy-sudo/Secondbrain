---
source: https://dev.to/urvvil/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-5dij
captured: 2026-11-07
type: article
---

<!-- Paste the source below as-is. Don't edit after capture. -->

<!--
Capture note: this is a section-by-section paraphrase of the article, not the
full text. The fetch tool returns summaries rather than verbatim copy, and the
article is someone else's copyrighted work. The URL above is the canonical text.
-->

# Andrej Karpathy's LLM Wiki: Create your own knowledge base

- **Author:** Urvil Joshi (dev.to/urvvil)
- **Published:** 2026-04-20 (dev.to also lists a 2026-05-27 crosspost date)
- **Tags:** artificialintelligence, productivity, rag, knowledgemanagement

## The Tweet That Started It

- Karpathy tweeted on 2026-04-02 about using LLMs to build personal knowledge bases.
- He followed up with a GitHub gist, `llm-wiki.md`, which he calls an "idea file." You paste it into an agent such as Claude Code or Codex, and the agent builds the setup for you.

## The Core Idea: Stop Retrieving. Start Compiling.

- The LLM builds a persistent wiki once and keeps it current, rather than re-reading raw documents for every question.
- Compiler analogy: raw sources are the source code, and the wiki is the compiled binary.
- For each new document, the LLM pulls out key information, updates pages, revises summaries, flags contradictions, and adds cross-links.
- The human curates sources and asks questions. The LLM does the summarizing, cross-referencing, and filing.

## The Three-Layer Architecture

1. **Raw sources:** immutable inputs (PDFs, articles, notes). The LLM reads them and never edits them, so the wiki can be rebuilt from them.
2. **The wiki:** markdown files the LLM owns outright: entity pages, concept pages, summaries, an index, and a log.
3. **The schema:** a CLAUDE.md or AGENTS.md file that sets conventions, page structure, and ingest and query rules.

## The Three Operations

- **Ingest:** adding a source makes the LLM write a summary page and update related pages, links, and contradiction flags. One source can touch many pages.
- **Query:** questions are answered from the synthesized wiki, not the raw files. Good answers can be saved back into the wiki as new pages.
- **Lint:** periodic audits for contradictions, orphan pages with no inbound links, and concepts that are mentioned but have no page.

## Let's Actually Build One

- Needs: an agent (Claude Code or Codex), Obsidian as a free viewer, and a local folder as the vault.
- Step 1: create a project folder with a `raw/` directory.
- Step 2: open the agent in that folder and paste one message that gives it Karpathy's gist and asks it to interview you before building.
- Step 3: the agent asks about topic, source types, expected volume, and page types.
- Step 4: the author's demo covers AI research and software philosophy, with 10 to 20 sources and concept, essay, and author pages. The agent writes CLAUDE.md and creates `wiki/index.md` and `wiki/log.md`.
- Step 5: ingest two demo sources, Rich Sutton's "The Bitter Lesson" and Karpathy's "Software 2.0." The page tree has sources, concepts, examples, and people folders. The second ingest updates existing pages and adds a cross-link the author didn't write.
- Step 6: ask a synthesis question (where the two authors agree and disagree). The answer comes from wiki pages, not the PDFs, and can be filed back into the vault.
- Step 7: open the folder in Obsidian and use graph view to see pages as nodes and links as edges.

## RAG vs LLM Wiki: The Honest Comparison

- Neither approach wins outright; they fit different problems.
- **RAG:** large, frequently changing corpora that need exact source citations.
- **LLM wiki:** smaller, curated collections (roughly 100 to 500 sources) where synthesis across sources matters.
- **Caveats:** ingest is costly; answers sit one or two steps removed from the raw source; updates need re-ingestion; and errors can harden into "facts" that spread across linked pages. The author recommends regular lint passes and spot-checking pages against raw sources.

## Why This Actually Matters

- Ties the idea to Vannevar Bush's 1945 Memex, a personal store where the links between documents matter as much as the documents.
- Personal wikis usually die because upkeep (cross-references, summaries, contradiction tracking) costs more than they return. LLMs can now carry that upkeep.
- The human's job shifts from filing and searching to curating and questioning.

## Reference

- Links to Karpathy's tweet and gist, Claude Code, Obsidian, the two demo sources, and a YouTube video on the LLM wiki.
