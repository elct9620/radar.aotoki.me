# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is Aotokitsuruya's Technology Radar, a static site built using the AOE Technology Radar generator (v4), which is based on Next.js. The radar showcases technologies the author uses or has used, organized by quadrants (Languages & Frameworks, Methods & Patterns, Platforms & Operations, Tools) and rings (Adopt, Trial, Assess, Hold).

## Build Commands

- `npm install` - Install dependencies
- `npm run build` - Build the static radar site (output goes to `./build` folder)
- `npm run serve` - Run development server at http://localhost:3000/

## Project Structure

```
.
├── config.json          # Radar configuration (quadrants, rings, colors, metadata)
├── about.md            # Content for the "About" page
├── custom.css          # Custom styling overrides
├── public/             # Static assets (logo, favicon, images)
│   └── images/         # Images referenced in radar entries
└── radar/              # Radar entries organized by release date
    └── YYYY-MM-DD/     # Release folders (e.g., 2024-10-01, 2025-01-01)
        └── *.md        # Individual technology entries
```

## Technology Entries

Each radar entry is a Markdown file in `radar/YYYY-MM-DD/` with frontmatter:

```markdown
---
title: "Technology Name"
ring: adopt|trial|assess|hold
quadrant: languages-and-frameworks|methods-and-patterns|platforms-and-services|tools
tags: [tag1, tag2]
featured: true|false  # Optional, default true
---

Markdown content describing the technology.
```

**Important conventions:**
- Filename acts as the identifier (e.g., `claude-code.md`)
- Items with the same filename in newer releases will merge/update older entries
- Images should be placed in `public/images/` and referenced as `/images/filename.png`

## Configuration

The `config.json` defines:
- `basePath`: URL path (`/` for root)
- `baseUrl`: Full deployment URL (https://radar.aotoki.me)
- `editUrl`: Template for edit links with `{id}` and `{release}` placeholders
- `quadrants[]`: Four categories with id, title, description, color
- `rings[]`: Four rings with id, title, description, color, radius, strokeWidth
- `social[]`: Footer social links

## Deployment

The site is deployed via GitHub Actions (`.github/workflows/main.yml`) to GitHub Pages on push to `main`:
1. Builds with `npm run build`
2. Uploads `./build` folder
3. Deploys to GitHub Pages

## Adding New Entries

1. Create a new release folder if needed: `radar/YYYY-MM-DD/`
2. Add a `.md` file with proper frontmatter
3. Ensure `ring` and `quadrant` values match those in `config.json`
4. Build locally with `npm run build` to verify
