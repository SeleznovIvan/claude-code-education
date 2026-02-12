# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a Claude Code plugin marketplace repository. Users can add this marketplace and install educational plugins from it.

## Key Files

- `.claude-plugin/marketplace.json` - Marketplace manifest listing available plugins
- `docs/MARKETPLACE-SETUP.md` - Reference documentation for marketplace setup

## Plugin Installation Flow

```bash
# Add marketplace (one-time)
claude plugin marketplace add github:SeleznovIvan/claude-code-education

# Install plugins
claude plugin install cc-course@claude-code-education
```

## Available Plugins

- **cc-course** - Interactive 5-module course for learning Claude Code (pinned to v0.1-alpha)

## Adding New Plugins

Add entries to the `plugins` array in `.claude-plugin/marketplace.json` with:
- `name`, `source` (github repo + optional ref), `description`, `version`, `author`, `keywords`, `category`
