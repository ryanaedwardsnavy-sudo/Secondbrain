---
title: How this second brain works
type: brief
audience: Ryan
created: 2026-11-07
built_from:
  - wiki/llm-wiki-pattern.md
  - wiki/llm-wiki-operations.md
  - wiki/llm-wiki-vs-rag.md
  - wiki/anthropic-repos.md
  - README.md
  - docs/iphone-setup.md
---

# How this second brain works

**Bottom line:** You save sources and ask questions. Claude does the filing, linking, and upkeep. You can do all of it from your iPhone through GitHub issues.

## What it is

- A GitHub repo that doubles as an Obsidian vault. Open the folder in Obsidian and the `[[wikilinks]]` and graph view just work.
- Three folders, one direction of flow:

```text
raw/  ──ingest──▶  wiki/  ──compile──▶  output/
(sources, never edited)  (distilled, linked notes)  (briefs, plans, posts)
```

- The layout copies the raw → wiki → output setup from @imryven's "How to Build a Second Brain With Claude and Obsidian," which surfaced in the X post that started this repo.

## The method behind it

- **Karpathy's LLM wiki pattern:** an LLM compiles raw sources into a linked markdown wiki once, then keeps it current. Questions get answered from the wiki, not by re-reading sources.
- **Three layers:** `raw/` holds the immutable evidence, `wiki/` holds the notes Claude maintains, and `CLAUDE.md` is the rulebook. `output/` adds a deliverables stage on top.
- **Division of labor:** you curate and ask. Claude summarizes, cross-links, files, and flags contradictions.
- **Why it lasts:** personal wikis usually die because upkeep costs more than it returns. Here the LLM carries the upkeep.
- **Why not RAG:** this is a small, curated collection where connecting ideas matters most, which suits a wiki. The main risk is a summary error spreading through linked notes. The guard is that every note cites its `raw/` source, so any claim can be spot-checked.

## The loop: ingest, ask, lint

| Step | What you do | What Claude does |
| --- | --- | --- |
| **Ingest** | Open an "Ingest a source" issue with a link, pasted text, or a screenshot | Saves it to `raw/`, updates or creates wiki notes, updates the index and log, and opens a PR link |
| **Ask** | Open an "Ask the second brain" issue ("what do I have on X?" or "compile a brief on Y") | Answers from `wiki/` only and says when it has nothing. Drafts go to `output/`. Answers that combine 2+ notes get filed back as new wiki notes |
| **Lint** | Nothing; it runs every Monday morning on GitHub | Fixes orphans, broken links, index drift, oversized notes, missing sources, and contradictions |

Rules Claude follows: update an existing note before creating a new one, paraphrase instead of pasting, keep notes under about 400 words, and flag conflicts rather than resolving them silently.

## Day to day from your iPhone

**Capture (no setup):**

1. GitHub app → **Secondbrain** → **Issues** → **New** → **Ingest a source**.
2. Paste the text, link, or screenshot and submit. For X posts, paste the text; those links usually can't be fetched.
3. In about a minute Claude replies with what it filed and a **Create PR** link. Tap it → **Create pull request** → **Merge**.
4. One-tap shortcut: in Safari, open `github.com/ryanaedwardsnavy-sudo/Secondbrain/issues/new/choose` → **Share** → **Add to Home Screen**.

**Ask:** same path, but pick **Ask the second brain**.

**Browse and edit in Obsidian:**

- **Smoothest:** Working Copy + Obsidian. Clone in Working Copy, open the folder as a vault in Obsidian. Pull before reading; commit and push after editing (pushing needs Working Copy's paid unlock).
- **Free:** Obsidian alone with the community **Git** plugin and a fine-grained GitHub token scoped to this repo.
- In the graph, raw is blue, wiki is orange, and output is green.

```text
see something  → Ingest issue → Claude files it → merge → it shows up in the graph
need something → Ask issue    → Claude answers from your notes (or drafts into output/)
```

## Gaps

- [[second-brain-method]] is linked from two notes but has no source yet. Ingest @imryven's original article to fill it.

## Built from

- [[llm-wiki-pattern]]
- [[llm-wiki-operations]]
- [[llm-wiki-vs-rag]]
- [[anthropic-repos]]
- `README.md` and `docs/iphone-setup.md` (repo docs, as requested)
