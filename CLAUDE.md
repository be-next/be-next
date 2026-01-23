# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **GitHub Profile Repository** for user `be-next`. It automatically generates and maintains a dynamic GitHub profile README using GitHub Actions workflows and the dōteki tool.

## Architecture

The repository uses two main automation systems:

1. **dōteki** (`doteki.toml`) - Generates dynamic README content by pulling blog posts from an RSS feed (https://idle-ti.me/atom.xml)
2. **GitHub Stats Cards** - Generates SVG statistics cards showing GitHub activity and language usage

All automation runs via GitHub Actions on a daily schedule (around 2:21-2:31 AM UTC) and on push events.

## Key Files

- `doteki.toml` - Configuration for dynamic README generation (blog posts, timestamps)
- `README.md` - The profile README with template markers for dōteki
- `.github/workflows/doteki.yml` - Workflow that runs dōteki to update README content
- `.github/workflows/github_readme_stats.yml` - Workflow that generates stats SVG cards
- `profile/` - Contains generated SVG assets (stats and language cards in light/dark modes)

## Development Notes

- No build/test/lint commands - this is a configuration-driven repository
- All generated SVGs in `profile/` are version controlled
- Commit messages use emoji prefixes (e.g., `👷 Update README cards`)
- Renovate handles automated dependency updates for GitHub Actions
