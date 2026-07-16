# Awesome Agent Skins [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> AI Agent 桌面端的皮肤、主题与换肤工具精选列表 — Codex、Claude Desktop、Cursor、Antigravity 等。

[English](README.md) | 简体中文

你的 AI 编程助手是你每天盯几个小时的应用。Agent 皮肤让你给它的界面换脸——配色、壁纸、角色、完整视觉身份——不碰官方安装包，不动你的 API 配置。

<img src="https://raw.githubusercontent.com/Fei-Away/Codex-Dream-Skin/main/docs/images/gallery/skin-03.jpg" alt="通过 CDP 注入换肤后的 Codex 桌面端" width="800">

<sup>运行时换肤后的 Codex 桌面端。图片来自 Codex-Dream-Skin 项目（MIT），见下文条目。</sup>

## 目录

- [快速上手](#快速上手)
- [宿主一览](#宿主一览)
- [Codex](#codex)
- [Claude Desktop](#claude-desktop)
- [Cursor](#cursor)
- [Antigravity](#antigravity)
- [Windsurf](#windsurf)
- [Zed 与 Warp](#zed-与-warp)
- [跨宿主与元项目](#跨宿主与元项目)
- [注入引擎与框架](#注入引擎与框架)
- [画廊与市场](#画廊与市场)
- [讨论](#讨论)
- [词义辨析](#词义辨析)
- [空缺与机会](#空缺与机会)

## 快速上手

选你的应用，一分钟开始换肤（下表为纯文本指路，链接见对应章节）：

| 你在用…           | 怎么做                                                                 |
| ----------------- | ---------------------------------------------------------------------- |
| Codex 桌面端      | 装 Codex-Dream-Skin 上完整图片皮肤，或从 DexThemes 导入原生主题字符串  |
| Claude Desktop    | 尚无成熟方案（仅一个 Linux-only 项目）——整个生态最大的空缺             |
| Cursor / Windsurf | 装 vscode-custom-ui-style 加背景图和自定义 CSS，或任意 VS Code 配色主题 |
| Antigravity       | 通过 Open VSX 装任意 VS Code 配色主题——教程见 Antigravity 章节         |
| Zed / Warp        | 只有原生主题画廊——注入不适用                                           |

换肤有三种方式：**原生主题**（宿主自带的主题系统——导入字符串、JSON、`.tmTheme`）、**CDP 注入**（以 loopback 调试端口启动 Electron 应用，运行时注入 CSS/图片——不改文件、完全可还原）、**Loader 注入**（VS Code 系扩展给 `workbench.html` 打补丁加载自定义 CSS/JS）。下文每个条目都标注了所用方式。

## 宿主一览

| 宿主                  | 内核                    | CDP 注入       | 原生主题               |
| --------------------- | ----------------------- | -------------- | ---------------------- |
| ChatGPT/Codex 桌面端  | Electron（已合并为一个应用） | ✅（震中）     | ✅（`codex-theme-v1`） |
| Claude Desktop        | Electron                | ✅（几乎无人开发） | ❌                     |
| Cursor                | Electron（VS Code fork） | ✅             | ✅（VS Code 主题）     |
| Antigravity           | Electron（VS Code fork） | ✅             | ✅（VS Code 主题）     |
| Windsurf              | Electron（VS Code fork） | ✅             | ✅（VS Code 主题）     |
| Zed                   | 原生（Rust/GPUI)        | ❌             | ✅（JSON 主题）        |
| Warp                  | 原生（Rust）            | ❌             | ✅（YAML 主题）        |

注：ChatGPT 桌面端早期是原生（SwiftUI）应用；当前 ChatGPT/Codex 已合并为一个 Electron 应用（bundle `com.openai.codex`），因此 CDP 注入适用。

## Codex

震中——绝大多数 agent 换肤活动都在这里。Codex 于 2026 年 3 月上线原生主题系统，随后引爆了一波远超调色范畴的第三方 CDP 注入工具（完整背景图、"会呼吸的脸"）。

### CDP 注入皮肤与工具

- [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin) - 源头项目（数日破 5k star）。Loopback CDP 注入给 Codex 换上完整图片皮肤，不碰 `.app` 和 `app.asar`，可还原。
- [CodeDrobe/codex-skill](https://github.com/CodeDrobe/codex-skill) - 开源换肤 Skill，带 AI 主题生成器和跨平台运行时。
- [HeiGeAi/heige-codex-skin-studio](https://github.com/HeiGeAi/heige-codex-skin-studio) - "一张图=一个主题"，macOS 一键换肤，应用内切换菜单。
- [xnydl/codex-dream-skin](https://github.com/xnydl/codex-dream-skin) - macOS 和 Windows 换肤 Skill，世事宜AI 免费分发。
- [tree0519/Codex-Dream-Skin-Forge](https://github.com/tree0519/Codex-Dream-Skin-Forge) - Dream-Skin 分支，增加 Windows 多主题包和应用内切换。
- [aiwenjie777/codex-skin-switcher](https://github.com/aiwenjie777/codex-skin-switcher) - 皮肤管理与切换器。
- [kongxcer555/codex-skin-builder](https://github.com/kongxcer555/codex-skin-builder) - 构建和定制皮肤的 Skill。
- [z0rgoyok/codex-theme-controller](https://github.com/z0rgoyok/codex-theme-controller) - macOS 工具，通过 CDP 应用配色主题。
- [fantuan-lab/codex-skin-market](https://github.com/fantuan-lab/codex-skin-market) - 基于 Dream-Skin 的皮肤实验室（macOS/Windows）。
- [XVibeCoding/codex-skin-studio](https://github.com/XVibeCoding/codex-skin-studio) - 基于 Dream-Skin（MIT）的非官方主题工作室。

还有大量小型分支和 Skill——欢迎 PR 补充值得收录的项目。

### 原生主题合集

- [jstxn/codex-themes](https://github.com/jstxn/codex-themes) - 原生导入字符串主题合集。
- [shaw-baobao/codex-themes](https://github.com/shaw-baobao/codex-themes) - 带预览图的可导入主题字符串。
- [lafllamme/codex-themes](https://github.com/lafllamme/codex-themes) - 把 `.itermcolors` 配色转成 Codex JSON 预设。
- [ychampion/codex-themes](https://github.com/ychampion/codex-themes) - 主题合集。

### 教程

- [Codex App 主题与自定义](https://codex.danielvaughan.com/2026/03/30/codex-app-theming-customisation/) - `codex-theme-v1` 格式、外观面板、导入字符串与合作主题详解。

## Claude Desktop

Electron 应用，CDP 注入技术上可行——但这块几乎无人开发。

- [patrickjaja/claude-desktop-bin](https://github.com/patrickjaja/claude-desktop-bin) - 非官方 Linux 包（550+ star），带完整自定义主题系统：通过 Electron `webContents.insertCSS()` 向所有 WebContents（含内嵌 `claude.ai` iframe）注入 CSS，自带主题目录。最接近 Dream-Skin 的 Claude 方案，但走 asar 补丁且仅限 Linux。
- [0326/Claude-Dream-Skin](https://github.com/0326/Claude-Dream-Skin) - 把 Dream-Skin 概念移植到 Claude 的早期占位项目。跨平台的 Claude CDP 换肤工具至今不存在。

## Cursor

VS Code fork——继承了成熟的 loader 生态。尚无专属的"Cursor 皮肤"品牌。

- [subframe7536/vscode-custom-ui-style](https://github.com/subframe7536/vscode-custom-ui-style) - 当前主流 loader（370+ star）。向编辑器和 webview 注入 CSS/JS、背景图、统一字体、修改 Electron 窗口参数。fork 上可用（有 CSP 限制）。
- [be5invis/vscode-custom-css](https://github.com/be5invis/vscode-custom-css) - 经典自定义 CSS/JS loader（1k+ star），Cursor 可用。
- [diogomoretti/hexxa-theme](https://github.com/diogomoretti/hexxa-theme) - Cursor AI 和 VS Code 的热门配色主题。

## Antigravity

VS Code fork。目前只有原生主题——没有 Antigravity 专属注入工具（通用 VS Code loader 适用）。

- [nik-holo/montexia-theme](https://github.com/nik-holo/montexia-theme) - 面向 Cursor、Antigravity、Windsurf 的深色主题。
- [Antigravity 换主题教程](https://agentpedia.codes/blog/change-antigravity-theme-guide) - 原生主题与 Open VSX 安装攻略。

## Windsurf

VS Code fork。没有专属换肤引擎——Cursor 章节列的两个 loader 在这里都能用。

- [eashansinha/windsurf-theme-dark](https://github.com/eashansinha/windsurf-theme-dark) - Windsurf 简洁深色配色主题。

## Zed 与 Warp

这两个宿主不是 Electron，CDP/CSS 注入不适用——只有原生主题格式。

- [labithiotis/zed-themes](https://github.com/labithiotis/zed-themes) - 在浏览器里浏览、预览、编辑 Zed 主题。
- [huacnlee/zed-theme-macos-classic](https://github.com/huacnlee/zed-theme-macos-classic) - Zed 的经典 macOS 风格主题家族（160+ star）。
- [RLabs-Inc/rlabs](https://github.com/RLabs-Inc/rlabs) - 包含 Warp 终端主题生成器等多种主题工具。

## 跨宿主与元项目

- [arvinxx/agent-skin-skills](https://github.com/arvinxx/agent-skin-skills) - "AI agent 桌面端一键沉浸式换肤"，签名安全的 CDP 注入。定位多宿主，目前仅支持 Codex——最接近通用 agent 换肤引擎的现存项目。
- [joeynyc/hermes-skins](https://github.com/joeynyc/hermes-skins) - Hermes CLI agent 的自定义皮肤（500+ star）——banner 配色、spinner、标签、ASCII art。证明皮肤概念可以延伸到终端 agent。
- [Hermes Agent 官方皮肤文档](https://hermes-agent.nousresearch.com/docs/user-guide/features/skins) - Hermes 官方皮肤文档——把皮肤做成一方功能的宿主。
- [Skales](https://getskales.app/) - 本地优先的 AI 桌面 agent，自带皮肤（Gecko、Bubbles、Capybara）——皮肤即一方功能。

## 注入引擎与框架

皮肤工具背后可复用的底层机制。CDP 方案：以绑定 loopback 的 `--remote-debugging-port` 启动 Electron 应用，通过 Chrome DevTools Protocol 驱动——Dream-Skin 及其后代的实现机制。asar 补丁方案：通过 Electron `webContents.insertCSS()` 注入 CSS（claude-desktop-bin 采用）。VS Code 系 loader 则给 `workbench.html` 打补丁。

- [magicdawn/vsc-custom-css-cli](https://github.com/magicdawn/vsc-custom-css-cli) - VS Code 自定义 CSS loader 的 CLI 版。
- [KemonoServal/electron-inject-dark-slack](https://github.com/KemonoServal/electron-inject-dark-slack) - 向 Slack 注入 CSS——整个 Electron 换肤品类的先例，与 BetterDiscord 同源。
- [Codex++ 解析文章](https://we0.ai/articles/codex-plus-plus-tutorial-codex-desktop-enhancement) - 用同一套 CDP 机制注入行为级增强的第三方启动器（Tauri/React + 用户脚本）。

## 画廊与市场

- [DexThemes](https://www.dexthemes.com/) - 通过原生导入字符串发现和创作 Codex 主题的社区画廊（非注入）。与 OpenAI 无隶属关系。

## 讨论

- [Gorden_Sun 的 X 帖](https://x.com/Gorden_Sun/status/2032843686682439909) - Codex 原生换肤支持的发布讨论帖（"科技以换壳为本"）。
- [servasyy_ai 的 X 帖](https://x.com/servasyy_ai/status/2077559536760873301) - 一位开发者的付费皮肤店计划被开源的 Dream-Skin 抢先——这个领域真实商业信号的记录。

## 词义辨析

"Agent skin" 一词含义重载。本列表只收录**视觉皮肤**。不收录人格/提示词"皮肤"——例如 [azw293/agent-skins](https://github.com/azw293/agent-skins)（agent 人格的 `SKIN.md` 标准与市场）——也不收录淹没搜索结果的游戏饰品仓库（Valorant、CS 等）。

## 空缺与机会

此前不存在覆盖这个领域的 awesome 列表——只有单宿主或人格向的合集。Claude Desktop 只有一个 Linux asar 补丁方案，没有跨平台 CDP 换肤工具，是最大的开发空缺。Antigravity 和 Windsurf 没有专属换肤引擎（仅 loader 可用）。Zed 和 Warp 是原生应用，注入不适用。

## 贡献

欢迎贡献！请先阅读[贡献指南](CONTRIBUTING.md)。条目必须真实、可用、与 AI agent 桌面端视觉换肤相关，并明确标注方式（原生 / CDP 注入 / loader）。
