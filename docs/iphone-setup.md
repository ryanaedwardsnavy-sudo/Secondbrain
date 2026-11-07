# Second Brain on your iPhone

There are two ways to use the vault from your phone. Use either or both.

## 1. Capture (no app setup needed)

Everything goes through GitHub issues, and Claude does the filing.

1. In the GitHub app (signed in as **sonarkills** or **ryanaedwardsnavy-sudo**), open **Secondbrain**, then **Issues**, then **New**.
2. Pick **Ingest a source**. Paste the text, a link, or a screenshot, and submit.
3. Within about a minute, Claude comments with what it filed and a **Create PR** link. Tap it, then **Create pull request**, then **Merge**.

To ask a question instead, pick **Ask the second brain** ("what do I have on X?" or "compile a brief on Y").

Shortcut: in Safari, open `github.com/ryanaedwardsnavy-sudo/Secondbrain/issues/new/choose`, then **Share**, then **Add to Home Screen**. That gives you a one-tap capture button.

## 2. Browse and edit in Obsidian

The repo ships shared vault settings in `.obsidian/`. When you open it, templates point at `templates/`, new notes land in `wiki/`, and the graph is colored by folder: raw is blue, wiki is orange, and output is green.

### Option A: Working Copy plus Obsidian (smoothest)

1. Install [Working Copy](https://workingcopy.app) and [Obsidian](https://obsidian.md) from the App Store.
2. In Working Copy: tap **+**, then **Clone repository**, then sign in to GitHub and pick **Secondbrain**. Pushing changes back requires Working Copy's paid unlock. Reading is free.
3. In Obsidian: tap **Open folder as vault**, then **Working Copy**, then **Secondbrain**.
4. To sync: in Working Copy, **Pull** before you read, and **Commit**, then **Push**, after you edit.

### Option B: Obsidian only (free, slower)

1. In Obsidian, create an empty vault named `Secondbrain`.
2. Install the community plugin **Git** (Settings, then **Community plugins**, then **Browse**, then **Git**).
3. Clone `https://github.com/ryanaedwardsnavy-sudo/Secondbrain` using a GitHub fine-grained token scoped to this repo only.
4. Use the plugin's **Pull** and **Commit-and-sync** commands.

## The loop

```text
see something → Ingest issue → Claude files it → merge → it shows up in Obsidian's graph
need something → Ask issue → Claude answers from your notes (or drafts into output/)
```
