# Cloud environment

Settings for the Claude Code cloud environment that works on this repo.

## Setup script

Paste this into the environment's **Setup script** field. It's safe to re-run.

```bash
# Setup script for the Claude Code cloud environment (Secondbrain).
# Paste into the environment's "Setup script" field, or run: bash scripts/setup-cloud-env.sh
# Idempotent and quiet: safe to re-run on every session start.
set -euo pipefail

need() { command -v "$1" >/dev/null 2>&1; }

# Search/JSON tools the skills rely on (rg for wiki lookups, jq for frontmatter/JSON work)
missing=()
need rg || missing+=(ripgrep)
need jq || missing+=(jq)
if [ ${#missing[@]} -gt 0 ]; then
  if need apt-get; then
    SUDO=""; [ "$(id -u)" -ne 0 ] && SUDO="sudo"
    $SUDO apt-get update -qq
    $SUDO apt-get install -y -qq "${missing[@]}" >/dev/null
  else
    echo "warn: could not install ${missing[*]} (no apt-get)" >&2
  fi
fi

# Markdown tooling: lint notes and parse frontmatter
if need npm; then
  need markdownlint-cli2 || npm install -g --silent markdownlint-cli2 >/dev/null 2>&1 || echo "warn: markdownlint-cli2 install failed" >&2
fi
if need python3; then
  python3 -c "import frontmatter" 2>/dev/null || \
    python3 -m pip install -q --break-system-packages python-frontmatter >/dev/null 2>&1 || \
    echo "warn: python-frontmatter install failed" >&2
fi

# Make sure the vault skeleton exists (empty dirs aren't tracked by git without .gitkeep)
mkdir -p raw/{articles,threads,transcripts,docs} wiki output templates

echo "secondbrain env ready: rg $(rg --version | head -1 | cut -d' ' -f2), jq $(jq --version 2>/dev/null)"
```

## Network access

Default (package registries only). Nothing extra is needed: web fetching goes through Claude's tools, not the shell.

## Variables

| Name | Value | Why |
| --- | --- | --- |
| `TZ` | `America/Los_Angeles` | Dated filenames match your calendar |

## Secrets

None for the cloud environment. The GitHub workflow uses a **repo secret** instead: `ANTHROPIC_API_KEY` or `CLAUDE_CODE_OAUTH_TOKEN` (see `.github/workflows/claude.yml`).
