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
- `output/`: things built *from* the wiki (briefs, posts, checklists, plans). These cite wiki notes, not raw.
- `templates/`: note templates. Don't put content here.

## Rules

1. **Update before you create.** Search `wiki/` (`rg -i "<term>" wiki/`) before making a new note. Merge into an existing note when the topic overlaps.
2. **Paraphrase, don't paste.** Wiki notes are summaries in our words. Quotes stay short (under 15 words) and attributed.
3. **Every claim has a source.** Each wiki note lists its raw sources under `## Sources`.
4. **Keep notes small.** If a note passes about 400 words, split it and link the pieces.
5. **Conflicts get flagged, not resolved silently.** If a new source contradicts a note, add a `## Open questions` entry citing both.
6. **Style:** Oxford comma, direct phrasing, no filler. Imperial units unless the source is metric and the context needs it.

## Skills

- `/ingest`: file a new source into `raw/` and fold it into `wiki/`.
- `/compile`: build a deliverable in `output/` from wiki notes.

## On GitHub (@claude)

When mentioned in an issue or PR, follow these same rules. An issue containing a URL or pasted text with "ingest" means: run the ingest workflow and open a PR. Never push directly to `main`.
