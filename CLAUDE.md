# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Claude Code plugin marketplace repository containing the `economist-style` plugin. The plugin applies The Economist style guide principles to written content, checking for clarity, precision, brevity, and dialect consistency.

## Repository Structure

```
economist-editor-plugin/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace manifest (lists available plugins)
├── economist-style/              # The plugin directory
│   ├── .claude-plugin/
│   │   └── plugin.json           # Plugin metadata and version
│   ├── skills/
│   │   └── economist-style/
│   │       ├── SKILL.md          # Main skill (auto-loaded, contains workflow)
│   │       └── reference/        # 13 detailed rule files (loaded on-demand),
│   │                             # e.g. ECONOMIST-SIGNATURE.md, CLARITY.md,
│   │                             # PRECISION.md, WORDS.md, PUNCTUATION.md
│   └── README.md
├── README.md                     # Marketplace README
└── LICENSE
```

## How the Plugin Works

1. **Skill loading**: Claude loads `SKILL.md` frontmatter at startup to understand when to activate
2. **Trigger**: User edits text or asks for style review → skill activates
3. **Progressive loading**: Main SKILL.md rules apply first; reference files load only when deeper checks are needed
4. **Dialect detection**: Plugin detects document's existing spelling/punctuation patterns and matches them (does not force British or American)

## Publishing

Published at https://github.com/TAJD/economist-style-guide-plugin — commit and push to release.

## User Installation

```
/plugin marketplace add TAJD/economist-style-guide-plugin
/plugin install economist-style@economist-style-plugins
```

(The name after `@` is the marketplace name from `marketplace.json`, not the repo name.)

## Version Updates

1. Edit files in `economist-style/`
2. Update version in `economist-style/.claude-plugin/plugin.json`
3. Commit and push

## Key Design Decisions

- **No external dependencies**: Works purely through Claude's language understanding (no Python/npm packages)
- **Dialect-neutral**: Matches existing document conventions rather than forcing British English
- **Progressive disclosure**: Reference files load on-demand to reduce context overhead
