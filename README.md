# Second Brain

A folder that gets smarter with every source saved. It's also an Obsidian vault: open this folder as a vault and the `[[wikilinks]]` just work.

```text
raw/      sources, saved as-is (never edited)
wiki/     distilled notes, one idea each, cross-linked — start at wiki/index.md
output/   things built from the wiki
templates/
```

## Using it

- **With Claude Code** (local or cloud): `/ingest <url or paste>` to file a source, `/compile <what you want>` to build something from the wiki. Rules live in `CLAUDE.md`. Skills live in `skills/` (also loadable as a Claude plugin via `.claude-plugin/plugin.json`).
- **From your phone via GitHub:** open an issue like `@claude ingest https://…` (or paste the text, since X links usually can't be fetched). Claude opens a PR with the raw capture and the wiki updates. Review, then merge.
- **In Obsidian:** browse, edit, and graph-view as normal. Commit when you're done.

## Setup checklist

- [ ] Add repo secret `ANTHROPIC_API_KEY` (or `CLAUDE_CODE_OAUTH_TOKEN`; see `.github/workflows/claude.yml`)
- [ ] Install the Claude GitHub app on this repo: <https://github.com/apps/claude>
