# Second Brain — operating rules for Claude

This repo is a personal knowledge base and an Obsidian vault. Sources go in raw, knowledge lives in the wiki, and finished work goes to output.

```text
raw/  ──ingest──▶  wiki/  ──compile──▶  output/
(untouched)        (distilled, linked)   (deliverables)
```

## Folders

- `raw/`: original sources, saved as-is. Subfolders: `articles/`, `threads/`, `transcripts/`, `docs/`.
  - **Never edit or delete anything in `raw/`.** It's the evidence trail.
  - Filename: `YYYY-MM-DD-short-slug.md`, with frontmatter `source:` (URL or origin) and `captured:` (date).
- `wiki/`: distilled notes, one concept per file, written in our own words.
  - Filename: `kebab-case-topic.md`. No dates in wiki filenames; notes evolve.
  - Every note uses `templates/wiki-note.md` and cites the raw file(s) it came from.
  - Link related notes with `[[wikilinks]]`. A link to a note that doesn't exist yet is fine; it flags a gap.
  - `wiki/index.md` is the map. Add every new note to it under the right heading.
  - `wiki/log.md` is the running record. Every ingest, lint, and filed answer adds an entry at the top.
- `output/`: things built *from* the wiki (briefs, posts, checklists, plans). These cite wiki notes, not raw.
- `templates/`: note templates. Don't put content here.

## Rules

1. **Update before you create.** Search `wiki/` (`rg -i "<term>" wiki/`) before making a new note. Merge into an existing note when the topic overlaps.
2. **Paraphrase, don't paste.** Wiki notes are summaries in our words. Quotes stay short (under 15 words) and attributed.
3. **Every claim has a source.** Each wiki note lists its raw sources under `## Sources`. A synthesis note (an answer filed back) may cite the wiki notes it was built from instead.
4. **Keep notes small.** If a note passes about 400 words, split it and link the pieces.
5. **Conflicts get flagged, not resolved silently.** If a new source contradicts a note, add a `## Open questions` entry citing both.
6. **Style:** Oxford comma, direct phrasing, no filler. Imperial units unless the source is metric and the context needs it.

## Skills

- `/ingest`: file a new source into `raw/` and fold it into `wiki/`.
- `/compile`: build a deliverable in `output/` from wiki notes.
- `/lint`: audit and repair the wiki (orphans, broken links, index drift, size, sources, contradictions). Runs weekly on GitHub.

## On GitHub (@claude)

When mentioned in an issue or PR, follow these same rules. Never push directly to `main`.

- **Ingest** (title starts with `@claude ingest`, or the `ingest` label): run the `skills/ingest` workflow on the issue's Link, Content, and screenshots. Put the "Why I'm saving this" line, if any, under the note's `## How I'd use this`. Commit to the branch and reply with what was filed.
- **Ask** (the `ask` label, or a question): answer in the reply from `wiki/` only, citing the notes as `wiki/<note>.md`. Say plainly when the wiki has nothing on it. If the request says compile, brief, write up, or draft, run `skills/compile` and commit the result to `output/`. If an answer synthesizes 2+ notes into something reusable, also file it as a new wiki note (citing those notes), add it to the index and log, and commit. That's how the wiki gets smarter from use, not just from new sources.
- **Lint** (the `lint` label, or asked to lint, clean up, or audit): run `skills/lint`, commit the fixes, and reply with the report.
- A Link you can't fetch (X/Twitter usually) is fine when the Content holds the text. If there's only a link and fetching fails, say so and ask for the text. Never invent content.
