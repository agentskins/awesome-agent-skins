# Awesome Agent Skins [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of skins, themes, and theming tools for AI agent desktop apps — Codex, Claude Desktop, Cursor, Antigravity, and more.

Your AI coding agent is the app you stare at for hours a day. Agent skins let you re-skin its interface — colors, wallpapers, characters, whole visual identities — without touching the official binary or your API config.

<img src="https://raw.githubusercontent.com/Fei-Away/Codex-Dream-Skin/main/docs/images/gallery/skin-03.jpg" alt="Codex desktop reskinned via CDP injection" width="800">

<sup>Codex desktop reskinned at runtime. Image from the Codex-Dream-Skin project (MIT), listed below.</sup>

_Keywords: codex skin, codex 皮肤, cursor theme, claude desktop theme, agent themes, AI desktop customization._

## Contents

- [Start Here](#start-here)
- [Host Apps at a Glance](#host-apps-at-a-glance)
- [Codex](#codex)
- [Claude Desktop](#claude-desktop)
- [Cursor](#cursor)
- [Antigravity](#antigravity)
- [Windsurf](#windsurf)
- [Zed and Warp](#zed-and-warp)
- [Cross-Host and Meta Projects](#cross-host-and-meta-projects)
- [Injection Engines and Frameworks](#injection-engines-and-frameworks)
- [Galleries and Marketplaces](#galleries-and-marketplaces)
- [Discussions](#discussions)
- [Disambiguation](#disambiguation)
- [Gaps and Opportunities](#gaps-and-opportunities)

## Start Here

Pick your app, get skinning in one minute. Names below are plain text — each links from its host section further down.

| You use…          | Do this                                                                                       |
| ----------------- | --------------------------------------------------------------------------------------------- |
| Codex desktop     | Install Codex-Dream-Skin for full image skins, or import a native theme string from DexThemes |
| Claude Desktop    | Nothing mature exists yet (one Linux-only option) — the biggest open gap in the ecosystem     |
| Cursor / Windsurf | Install vscode-custom-ui-style for backgrounds and custom CSS, or any VS Code color theme     |
| Antigravity       | Any VS Code color theme via Open VSX — guide linked in the Antigravity section                |
| Zed / Warp        | Native theme galleries only — no injection applies                                            |

How it works, in three flavors: **native theming** (the host's own theme system — config strings, JSON, `.tmTheme`), **CDP injection** (launch the Electron app with a loopback debug port, inject CSS/images at runtime — no file modification, fully reversible), and **loader injection** (a VS Code-family extension patches `workbench.html`). Every entry below is labeled with its approach.

## Host Apps at a Glance

| Host                  | Runtime                 | CDP Injection         | Native Themes          |
| --------------------- | ----------------------- | --------------------- | ---------------------- |
| ChatGPT/Codex desktop | Electron (unified app)  | Yes (epicenter)       | Yes (`codex-theme-v1`) |
| Claude Desktop        | Electron                | Yes (mostly untapped) | No                     |
| Cursor                | Electron (VS Code fork) | Yes                   | Yes (VS Code themes)   |
| Antigravity           | Electron (VS Code fork) | Yes                   | Yes (VS Code themes)   |
| Windsurf              | Electron (VS Code fork) | Yes                   | Yes (VS Code themes)   |
| Zed                   | Native (Rust/GPUI)      | No                    | Yes (JSON themes)      |
| Warp                  | Native (Rust)           | No                    | Yes (YAML themes)      |

Note: the ChatGPT desktop app was formerly native (SwiftUI). The current unified ChatGPT/Codex desktop app is Electron (bundle `com.openai.codex`), so CDP injection applies.

## Codex

The epicenter — the vast majority of agent-skin activity lives here. Codex shipped a native theme system in March 2026, which triggered a wave of third-party CDP-injection tools that go far beyond colors (full background images, "breathing face" UIs).

### CDP Injection Skins and Tools

- [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin) - The origin project (2.7k+ stars in days). Loopback CDP injection gives Codex a full image-based "breathing face" without touching `.app` or `app.asar`. Reversible.
- [CodeDrobe/codex-skill](https://github.com/CodeDrobe/codex-skill) - Open-source theming Skill with an AI theme generator and cross-platform runtime.
- [HeiGeAi/heige-codex-skin-studio](https://github.com/HeiGeAi/heige-codex-skin-studio) - One image equals one theme — one-click reskin for macOS with an in-app switcher menu.
- [xnydl/codex-dream-skin](https://github.com/xnydl/codex-dream-skin) - Reskin Skill for macOS and Windows, distributed free by 世事宜AI.
- [tree0519/Codex-Dream-Skin-Forge](https://github.com/tree0519/Codex-Dream-Skin-Forge) - Dream-Skin fork adding Windows multi-theme packs and in-app switching.
- [aiwenjie777/codex-skin-switcher](https://github.com/aiwenjie777/codex-skin-switcher) - Skin manager and switcher.
- [kongxcer555/codex-skin-builder](https://github.com/kongxcer555/codex-skin-builder) - Skill for building and customizing skins.
- [z0rgoyok/codex-theme-controller](https://github.com/z0rgoyok/codex-theme-controller) - Utility for macOS applying color themes via CDP.
- [fantuan-lab/codex-skin-market](https://github.com/fantuan-lab/codex-skin-market) - Nascent skin lab for macOS and Windows built on Dream-Skin.
- [XVibeCoding/codex-skin-studio](https://github.com/XVibeCoding/codex-skin-studio) - Unofficial theme studio based on Dream-Skin (MIT).

Many smaller forks and Skills exist — open a PR to surface notable ones.

### Native Theme Collections

- [jstxn/codex-themes](https://github.com/jstxn/codex-themes) - Theme collection using native import strings.
- [shaw-baobao/codex-themes](https://github.com/shaw-baobao/codex-themes) - Importable theme strings with previews.
- [lafllamme/codex-themes](https://github.com/lafllamme/codex-themes) - Converts `.itermcolors` palettes into Codex JSON presets.
- [ychampion/codex-themes](https://github.com/ychampion/codex-themes) - Theme collection.

### Guides

- [Codex App Theming and Customisation](https://codex.danielvaughan.com/2026/03/30/codex-app-theming-customisation/) - The `codex-theme-v1` format, Appearance panel, import strings, and partner themes.

## Claude Desktop

Electron, so CDP injection is technically viable — but the space is almost untapped.

- [patrickjaja/claude-desktop-bin](https://github.com/patrickjaja/claude-desktop-bin) - Unofficial Linux packages (550+ stars) with a full custom-theme system injecting CSS via Electron `webContents.insertCSS()` on every WebContents, including the nested `claude.ai` iframe. Bundled themes directory. The closest Claude analog to Dream-Skin, but asar-patch and Linux-only.
- [0326/Claude-Dream-Skin](https://github.com/0326/Claude-Dream-Skin) - Early placeholder attempt to port the Dream-Skin concept to Claude. No mature cross-platform CDP skin tool for Claude exists yet.

## Cursor

VS Code fork — inherits a mature loader-based ecosystem. No bespoke Cursor skin brand yet.

- [subframe7536/vscode-custom-ui-style](https://github.com/subframe7536/vscode-custom-ui-style) - Leading modern loader (370+ stars). Injects CSS/JS into editor and webview, background images, font unification, patches Electron window options. Works on forks with CSP caveats.
- [be5invis/vscode-custom-css](https://github.com/be5invis/vscode-custom-css) - The classic custom CSS/JS loader (1k+ stars). Works in Cursor.
- [diogomoretti/hexxa-theme](https://github.com/diogomoretti/hexxa-theme) - Popular color theme for Cursor AI and VS Code.

## Antigravity

VS Code fork. Native themes only so far — no injection tooling specific to Antigravity, though generic VS Code loaders apply.

- [nik-holo/montexia-theme](https://github.com/nik-holo/montexia-theme) - Dark theme targeting Cursor, Antigravity, and Windsurf.
- [Change Antigravity Theme Guide](https://agentpedia.codes/blog/change-antigravity-theme-guide) - Native theme and Open VSX install walkthrough.

## Windsurf

VS Code fork. No dedicated skin engine — the loaders listed under Cursor (custom-ui-style and custom-css) both work here.

- [eashansinha/windsurf-theme-dark](https://github.com/eashansinha/windsurf-theme-dark) - Simple dark color theme for Windsurf.

## Zed and Warp

These hosts are not Electron, so CDP/CSS injection does not apply — only native theme formats.

- [labithiotis/zed-themes](https://github.com/labithiotis/zed-themes) - Explore, preview, and edit Zed themes in the browser.
- [huacnlee/zed-theme-macos-classic](https://github.com/huacnlee/zed-theme-macos-classic) - Classic macOS-style theme family for Zed (160+ stars).
- [RLabs-Inc/rlabs](https://github.com/RLabs-Inc/rlabs) - Includes a Warp terminal theme generator among other theming tools.

## Cross-Host and Meta Projects

- [arvinxx/agent-skin-skills](https://github.com/arvinxx/agent-skin-skills) - One-click immersive skins for AI agent desktop apps via signature-safe CDP injection. Framed multi-host, currently Codex-only — the closest existing project to a universal agent-skin engine.
- [joeynyc/hermes-skins](https://github.com/joeynyc/hermes-skins) - Custom skins (500+ stars) for the Hermes CLI agent — banner colors, spinners, labels, ASCII art. Proof the skin metaphor extends to terminal agents.
- [Hermes Agent Skins Docs](https://hermes-agent.nousresearch.com/docs/user-guide/features/skins) - Official skins documentation for the Hermes agent — a first-party host embracing the skin concept.
- [Skales](https://getskales.app/) - Local-first AI desktop agent shipping with built-in skins (Gecko, Bubbles, Capybara) — skins as a first-party feature.

## Injection Engines and Frameworks

The reusable substrates skin tools are built on. The CDP approach launches an Electron app with `--remote-debugging-port` bound to loopback and drives it over the Chrome DevTools Protocol — the mechanism behind Dream-Skin and its descendants. The asar-patch approach injects CSS via Electron `webContents.insertCSS()` (used by claude-desktop-bin). VS Code-family loaders patch `workbench.html` instead.

- [magicdawn/vsc-custom-css-cli](https://github.com/magicdawn/vsc-custom-css-cli) - CLI patcher equivalent of the VS Code custom-CSS loaders.
- [KemonoServal/electron-inject-dark-slack](https://github.com/KemonoServal/electron-inject-dark-slack) - Inject CSS into Slack — prior art for the whole Electron-reskin category, alongside BetterDiscord.
- [Codex++ Writeup](https://we0.ai/articles/codex-plus-plus-tutorial-codex-desktop-enhancement) - Third-party launcher injecting behavioral enhancements via the same CDP substrate (Tauri/React plus user scripts).

## Galleries and Marketplaces

- [DexThemes](https://www.dexthemes.com/) - Community gallery to discover and create Codex themes via native import strings (not injection). Not OpenAI-affiliated.

## Discussions

- [Gorden_Sun on X](https://x.com/Gorden_Sun/status/2032843686682439909) - Announcement thread for Codex native reskin support (科技以换壳为本).
- [servasyy_ai on X](https://x.com/servasyy_ai/status/2077559536760873301) - Thread from a developer whose paid skin-shop plan was pre-empted by the open-source Dream-Skin — the live commercial signal in this space.

## Disambiguation

The term "agent skin" is overloaded. This list covers visual skins only. It does not cover persona/prompt skins — for example [azw293/agent-skins](https://github.com/azw293/agent-skins), a `SKIN.md` standard and marketplace for agent personalities — or game cosmetic repos (Valorant, Counter-Strike) that flood the search results.

## Gaps and Opportunities

No prior awesome list existed for this space — it had only single-host or persona-oriented collections. Claude Desktop has only a Linux asar-patch theme system and no cross-platform CDP skin tool, making it the biggest open build opportunity. Antigravity and Windsurf have zero bespoke skin engines (loader-based only). Zed and Warp are native hosts where injection does not apply.

## Contributing

Contributions welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first. Entries must be real, working, and relevant to visually skinning AI agent desktop apps, with the approach (native, CDP injection, or loader) clearly labeled.
