# Awesome Agent Skins [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of skins, themes, and theming tools for AI **agent desktop apps** — Codex, Claude Desktop, Cursor, Antigravity, and more.

Your AI coding agent is the app you stare at for hours a day. **Agent skins** let you re-skin its interface — colors, wallpapers, characters, whole visual identities — without touching the official binary or your API config. This list tracks every skin, theme, injection engine, gallery, and guide across the ecosystem.

*Keywords: codex skin · codex 皮肤 · cursor theme · claude desktop theme · agent themes · AI desktop customization.*

## Contents

- [What Is an Agent Skin?](#what-is-an-agent-skin)
- [Host Apps at a Glance](#host-apps-at-a-glance)
- [Codex](#codex)
- [Claude Desktop](#claude-desktop)
- [Cursor](#cursor)
- [Antigravity](#antigravity)
- [Windsurf](#windsurf)
- [Native Hosts: ChatGPT · Zed · Warp](#native-hosts-chatgpt--zed--warp)
- [Cross-Host & Meta Projects](#cross-host--meta-projects)
- [Injection Engines & Frameworks](#injection-engines--frameworks)
- [Galleries & Marketplaces](#galleries--marketplaces)
- [Discussions](#discussions)
- ["Agent Skin" Disambiguation](#agent-skin-disambiguation)
- [Contributing](#contributing)

## What Is an Agent Skin?

There are **three distinct ways** to customize an agent desktop app. Conflating them is the most common mistake — this list keeps them separate:

1. **Native / built-in theming** — the host ships its own theme system (config strings, JSON, `.tmTheme`). No injection. Every VS Code fork and modern Codex build has this.
2. **CDP injection skins** — an external tool launches the Electron app with a remote-debugging port and injects CSS/JS/images via the Chrome DevTools Protocol at runtime. No file/`.asar` modification, fully reversible. This is the *Codex-Dream-Skin* pattern — the hot, novel category, and it **only works on Electron/Chromium hosts**.
3. **Extension / loader injection** — for VS Code–family editors, a marketplace extension patches `workbench.html` to load custom CSS/JS.

## Host Apps at a Glance

| Host | Runtime | CDP Injection | Native Themes |
|------|---------|---------------|---------------|
| **Codex desktop** | Electron | ✅ (epicenter) | ✅ `codex-theme-v1` |
| **Claude Desktop** | Electron | ✅ (mostly untapped) | ❌ |
| **Cursor** | Electron (VS Code fork) | ✅ | ✅ VS Code themes |
| **Antigravity** | Electron (VS Code fork) | ✅ | ✅ VS Code themes |
| **Windsurf** | Electron (VS Code fork) | ✅ | ✅ VS Code themes |
| **ChatGPT desktop** | Native (SwiftUI) | ❌ | ❌ OS appearance |
| **Zed** | Native (Rust/GPUI) | ❌ | ✅ JSON themes |
| **Warp** | Native (Rust) | ❌ | ✅ YAML themes |

## Codex

The epicenter — 90%+ of agent-skin activity lives here. Codex shipped a native theme system in March 2026, which triggered a wave of third-party **CDP-injection** tools that go far beyond colors (full background images, "breathing face" UIs).

### CDP Injection Skins & Tools

- [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin) ⭐~1273 — The origin project. Loopback CDP injection gives Codex a full image-based "breathing face" without touching `.app`/`app.asar`. Reversible.
- [CodeDrobe/codex-skill](https://github.com/CodeDrobe/codex-skill) ⭐~59 — Open-source theming Skill + AI theme generator + cross-platform runtime.
- [HeiGeAi/heige-codex-skin-studio](https://github.com/HeiGeAi/heige-codex-skin-studio) ⭐~35 — "One image = one theme" one-click reskin (macOS), in-app switcher menu.
- [xnydl/codex-dream-skin](https://github.com/xnydl/codex-dream-skin) ⭐~10 — macOS & Windows reskin Skill, distributed free by 世事宜AI.
- [tree0519/Codex-Dream-Skin-Forge](https://github.com/tree0519/Codex-Dream-Skin-Forge) ⭐~8 — Dream-Skin fork adding Windows multi-theme packs + in-app switching.
- [aiwenjie777/codex-skin-switcher](https://github.com/aiwenjie777/codex-skin-switcher) ⭐~6 — Skin manager / switcher.
- [kongxcer555/codex-skin-builder](https://github.com/kongxcer555/codex-skin-builder) ⭐~6 — Skill for building/customizing skins.
- [z0rgoyok/codex-theme-controller](https://github.com/z0rgoyok/codex-theme-controller) ⭐~4 — macOS utility applying color themes via CDP.
- Studios & nascent markets: [fantuan-lab/codex-skin-market](https://github.com/fantuan-lab/codex-skin-market), [XVibeCoding/codex-skin-studio](https://github.com/XVibeCoding/codex-skin-studio) — injection-based skin labs built on Dream-Skin.
- Many smaller forks/Skills exist (Lxcalibur, MuShan-bit, onewesong, anhao, charmber, ismoshushi, dkfjtang, et al.) — see [Contributing](#contributing) to surface notable ones.

### Native Theme Collections (import strings / `codex-theme-v1`)

- [jstxn/codex-themes](https://github.com/jstxn/codex-themes) ⭐~9 — Theme collection.
- [shaw-baobao/codex-themes](https://github.com/shaw-baobao/codex-themes) ⭐~5 — Importable theme strings with previews.
- [lafllamme/codex-themes](https://github.com/lafllamme/codex-themes) ⭐~5 — Converts `.itermcolors` palettes into Codex JSON presets.
- [ychampion/codex-themes](https://github.com/ychampion/codex-themes) ⭐~3 — Theme collection.

### Guides

- [Codex App Theming & Customisation](https://codex.danielvaughan.com/2026/03/30/codex-app-theming-customisation/) — the `codex-theme-v1` format, Appearance panel, import strings, partner themes.

## Claude Desktop

Electron — so CDP injection is technically viable, but the space is **almost untapped** (see [gaps](#key-gaps--opportunities)).

- [patrickjaja/claude-desktop-bin](https://github.com/patrickjaja/claude-desktop-bin) — Unofficial Linux packages with a full custom-theme system: injects CSS via Electron `webContents.insertCSS()` on every WebContents (incl. the nested `a.claude.ai` iframe). `customCss` supports raw CSS + variables; bundled `themes/` directory. The closest Claude analog to Dream-Skin — but asar-patch, Linux-only.
- [0326/Claude-Dream-Skin](https://github.com/0326/Claude-Dream-Skin) — Early placeholder attempt to port the Dream-Skin concept to Claude. No mature cross-platform CDP skin tool for Claude exists yet.

## Cursor

VS Code fork — inherits a mature loader-based ecosystem. No bespoke "Cursor skin" brand yet.

- [subframe7536/vscode-custom-ui-style](https://github.com/subframe7536/vscode-custom-ui-style) — Leading modern loader: injects CSS/JS into editor + webview, background images, font unification, patches Electron window options. Works on forks (with CSP caveats).
- [be5invis/vscode-custom-css](https://github.com/be5invis/vscode-custom-css) ⭐~1054 — The classic custom-CSS/JS loader; works in Cursor.
- [diogomoretti/hexxa-theme](https://github.com/diogomoretti/hexxa-theme) — Popular color theme for Cursor AI & VS Code.

## Antigravity

VS Code fork. **Native themes only so far** — no injection tooling specific to Antigravity (generic VS Code loaders apply).

- [nik-holo/montexia-theme](https://github.com/nik-holo/montexia-theme) — Dark theme targeting Cursor / Antigravity / Windsurf.
- [Change Antigravity Theme — guide](https://agentpedia.codes/blog/change-antigravity-theme-guide) — native theme + Open VSX install walkthrough.

## Windsurf

VS Code fork. No dedicated skin engine — loader-based only ([vscode-custom-ui-style](https://github.com/subframe7536/vscode-custom-ui-style), [be5invis/vscode-custom-css](https://github.com/be5invis/vscode-custom-css) both work).

## Native Hosts: ChatGPT · Zed · Warp

These are **not** Electron — CDP/CSS injection does **not** apply. Only native theme formats or OS-level tricks.

- **ChatGPT Desktop** (SwiftUI/native) — no custom-theme system; follows OS appearance. Users wanting skins swap to an Electron wrapper (e.g. [vincelwt/chatgpt-mac](https://github.com/vincelwt/chatgpt-mac)).
- **Zed** (Rust/GPUI) — rich native JSON theme ecosystem: [labithiotis/zed-themes](https://github.com/labithiotis/zed-themes) (explore/preview/edit), [huacnlee/zed-theme-macos-classic](https://github.com/huacnlee/zed-theme-macos-classic) ⭐~164, and many more on zed.dev extensions.
- **Warp** (Rust) — native YAML theme system; community generators like [RLabs-Inc/rlabs](https://github.com/RLabs-Inc/rlabs).

## Cross-Host & Meta Projects

- [arvinxx/agent-skin-skills](https://github.com/arvinxx/agent-skin-skills) — "One-click immersive skins for AI agent desktop apps — signature-safe CDP injection." Framed multi-host, currently Codex-only. The closest existing project to a universal agent-skin engine.

## Injection Engines & Frameworks

The reusable substrates a skin tool is built on:

- **Chrome DevTools Protocol (CDP)** via `--remote-debugging-port` — the mechanism behind Dream-Skin, HeiGeAi studio, z0rgoyok, arvinxx. Works on any Electron app.
- **Electron `webContents.insertCSS()` asar patch** — the patrickjaja/claude-desktop-bin approach.
- **VS Code `workbench.html` loaders** — [be5invis/vscode-custom-css](https://github.com/be5invis/vscode-custom-css), [subframe7536/vscode-custom-ui-style](https://github.com/subframe7536/vscode-custom-ui-style), [magicdawn/vsc-custom-css-cli](https://github.com/magicdawn/vsc-custom-css-cli).
- **Codex++** ([writeup](https://we0.ai/articles/codex-plus-plus-tutorial-codex-desktop-enhancement)) — third-party launcher injecting *behavioral* enhancements via the same CDP substrate (Tauri/React + user scripts).
- **Prior art** — [KemonoServal/electron-inject-dark-slack](https://github.com/KemonoServal/electron-inject-dark-slack) and BetterDiscord: the canonical Electron-reskin precedents this whole category descends from.

## Galleries & Marketplaces

- [DexThemes](https://www.dexthemes.com/) — Community gallery to discover & create Codex themes via native import strings (not injection). Not OpenAI-affiliated.

## Discussions

- [@Gorden_Sun](https://x.com/Gorden_Sun/status/2032843686682439909) — "Codex APP史诗级更新：支持换肤了，科技以换壳为本" (native reskin support announced).
- [@servasyy_ai](https://x.com/servasyy_ai/status/2077559536760873301) — a dev lamenting that the Codex skin idea was open-sourced before he could launch a paid "skin shop" — the live commercial signal in this space.

## "Agent Skin" Disambiguation

The term is overloaded. This list covers **visual skins** (approaches above). It does **not** cover:

- **Persona / prompt "skins"** — e.g. [azw293/agent-skins](https://github.com/azw293/agent-skins), a `SKIN.md` standard + marketplace for agent *personalities* (a naming collision worth knowing).
- **Game agent skins** — Valorant/etc. cosmetic repos that flood the search.

## Key Gaps & Opportunities

- **No prior `awesome-agent-skins` list existed** — the space had only single-host or persona-oriented lists.
- **Claude Desktop** has only a Linux asar-patch theme system — no cross-platform CDP skin tool. The biggest open build opportunity.
- **Antigravity & Windsurf** have zero bespoke skin engines (loader-based only).
- **ChatGPT · Zed · Warp** are native — injection dead ends.

## Contributing

Contributions welcome! Open a PR to add a skin, tool, gallery, or guide. Entries must be real, working, and relevant to *visually* skinning AI agent desktop apps. Keep the three approaches (native / CDP injection / loader) clearly labeled.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
