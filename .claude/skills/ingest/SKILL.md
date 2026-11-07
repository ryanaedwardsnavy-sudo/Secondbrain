---
name: ingest
description: File a new source (URL, pasted text, transcript, screenshot) into raw/ and fold its ideas into the wiki. Use when the user says ingest, save this, clip this, or add this to the second brain.
---

# Ingest a source

1. **Capture to raw.** Create `raw/<type>/YYYY-MM-DD-slug.md` from `templates/raw-source.md`. Paste the source as-is. If it's a URL you can't fetch, ask the user to paste the text or a screenshot. Don't invent the content.
2. **Find what it touches.** Pull out the 3–7 main ideas. For each, search the wiki first: `rg -il "<keyword>" wiki/`.
3. **Update or create notes.**
   - Overlapping note exists: add the new points, add the raw file under `## Sources`, and bump `updated:`.
   - No note exists: create `wiki/<topic>.md` from `templates/wiki-note.md`.
   - Contradicts an existing note: add it under `## Open questions` with both sources. Don't silently overwrite.
4. **Link.** Add `[[wikilinks]]` between related notes, and add new notes to `wiki/index.md`.
5. **Report.** List the raw file created and each wiki note created or updated, one line each.

Rules: never edit existing files in `raw/`. Paraphrase in wiki notes; quotes under 15 words.
