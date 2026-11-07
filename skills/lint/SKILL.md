---
name: lint
description: Audit and repair the second brain's wiki for orphans, unresolved links, oversized notes, missing sources, contradictions, and index drift. Use when the user says lint, clean up, health check, or audit the vault, and on the weekly schedule.
---

# Lint the wiki

Run each check, fix what's safe to fix, and report the rest.

## Checks

1. **Unresolved links:** `[[name]]` where `wiki/name.md` doesn't exist. Ignore links inside backticks (examples of syntax).
   - If an existing note clearly covers it, repoint the link.
   - If the concept is real and recurs in 2+ notes, list it as a **gap** (a note worth writing). Don't write it from memory.
   - Otherwise, leave the link as an intentional gap.
2. **Orphans:** wiki notes (other than `index.md` and `log.md`) with no inbound `[[links]]` from another note. Add a link from the most related note, and make sure the orphan is in `wiki/index.md`.
3. **Index drift:** every wiki note is listed in `wiki/index.md`, and every index entry exists. Fix both directions.
4. **Size:** notes over about 400 words. Split them, link the pieces, and update the index.
5. **Sources:** every wiki note has a `## Sources` section pointing at real `raw/` files. Flag any that don't. Never invent a source.
6. **Frontmatter:** `title`, `tags`, `created`, and `updated` are present. Bump `updated:` on any note you change.
7. **Contradictions:** skim notes that share tags for claims that disagree. Add an `## Open questions` entry to both, citing each source. Don't pick a winner.
8. **Stale paths:** references to files or folders that no longer exist in the repo.

## Useful commands

```bash
rg -o --no-filename '\[\[[^\]|#]+' wiki/ | sort | uniq -c        # every link target
ls wiki/                                                           # every note
rg -L '^## Sources' wiki/ --files-without-match                    # notes missing sources
for f in wiki/*.md; do echo "$(wc -w < "$f") $f"; done | sort -rn  # sizes
```

## Finish

- Append an entry to `wiki/log.md`: date, `lint`, and one line per fix.
- Report in this shape: **Fixed** (one line each), **Gaps worth a note** (concept, and which notes mention it), and **Needs Ryan** (judgment calls).
- Never edit `raw/`.
