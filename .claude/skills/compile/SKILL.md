---
name: compile
description: Build a deliverable (brief, post, checklist, plan, summary) in output/ from existing wiki notes. Use when the user asks to write, draft, or summarize something using what's in the second brain.
---

# Compile an output

1. **Scope it.** Confirm the deliverable type and audience in one line. Ask only if it's genuinely unclear.
2. **Gather.** Start at `wiki/index.md`, follow `[[links]]`, and use `rg -i` across `wiki/`. Work from wiki notes, not raw. If the wiki is missing something important, say so instead of filling it from memory.
3. **Write** `output/YYYY-MM-DD-slug.md` with frontmatter `built_from:` listing the wiki notes used.
4. **Cite.** End with a `## Built from` list of `[[wiki-note]]` links.
5. **Feed back.** If writing exposed a gap or a contradiction, add it to the relevant wiki note's `## Open questions`.

Style: Oxford comma, direct phrasing, no filler.
