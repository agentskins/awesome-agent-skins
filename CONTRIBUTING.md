# Contribution Guidelines

Thanks for helping map the agent-skin ecosystem! Please follow these rules so the list stays useful.

## What belongs here

Entries must be about **visually skinning/theming AI agent desktop apps** — skins, themes, injection engines, galleries, and guides for hosts like Codex, Claude Desktop, Cursor, Antigravity, Windsurf, Zed, Warp.

Out of scope: persona/prompt "skins" (see the Disambiguation section), game cosmetic repos, generic wallpaper packs, and anything that modifies signed application binaries in unsafe ways.

## Quality bar

- The project must be **real and working** — installable today, not a placeholder/empty repo.
- Label the approach clearly: **native theme**, **CDP injection**, or **loader/extension**.
- One-line description: what it does and which host it targets. No marketing language.
- Prefer the canonical/original project over forks unless the fork adds something substantial (say what).

## How to add an entry

1. Fork, then edit `README.md`.
2. Add your entry to the correct host section, keeping the existing format:
   `[owner/repo](url) — Description. (approach)`
3. Keep sections ordered roughly by stars/notability.
4. One entry per PR when possible; explain in the PR body why it belongs.

## Reporting dead links or abandoned projects

Open an issue titled `dead: <entry name>` — we prune entries that no longer work after host app updates.
