# AGENTS.md

This file provides guidance to AI coding agents when working with code in this repository.

## General Agent Rules

- When users ask questions, answer them instead of doing the work.

### Shell Rules

- Always use `rm -f` (never bare `rm`)
- Before running a series of `git` commands, confirm you are in the project root; if not, `cd` there first. Then run all subsequent `git` commands from that directory without the `-C` option.

## Project Overview

A personal Markdown notes repository. All content lives under `contents/`.

## Setup

Prerequisites: [mise](https://mise.jdx.dev)

```bash
mise run setup     # Install all tools
```

## Tools

Managed by mise (`mise.toml`):

- `markdownlint-cli2` — Markdown linter
- `mdsn` — Section number validator
- `mktoc` — Table of contents generator for `contents/*.md`
- `cspell` — Spell checker
- `actionlint` + `shellcheck` — GitHub Actions / shell linter
- `lefthook` — Git hooks manager

## Common Commands

| Command | Description |
| --- | --- |
| `mise run fix` | Auto-fix all issues |
| `mise run check` | Run all checks |
| `mise run fix-and-check` | Fix then check |
| `mise run md-fix` | Fix Markdown issues |
| `mise run md-check` | Check Markdown issues |

## Git Hooks

`pre-commit` and `pre-push` both run `mise run check` via lefthook.

## Markdown Style

- Unordered lists: dashes (`-`)
- Emphasis / strong: asterisks (`*`)
- No line length limit
- Inline HTML: only `<br>` is allowed
- 2-space indentation, LF line endings, trailing whitespace trimmed, final newline required
- Fenced code blocks must specify a language identifier
