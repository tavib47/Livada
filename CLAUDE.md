# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML website ("Livada Mea") — a personal Romanian-language orchard guide covering fruit tree pruning schedules, species-specific pruning instructions, and branch anatomy. Hosted on GitHub (tavib47/Livada).

## Architecture

Four standalone HTML files with all CSS and JS inlined (no build system, no frameworks, no package manager):

- **index.html** — Landing page hub linking to the three tool pages. Uses Google Fonts (Lora + DM Sans).
- **tabel_taieri_livada.html** — Filterable table of pruning schedules for 22 fruit tree varieties (10 species). Uses system fonts. JS handles species filter buttons.
- **ghid_taieri_pomi.html** — Detailed pruning instructions per species with tab-style navigation. Uses system fonts. JS toggles `.content` sections by species.
- **ghid_ramuri_pomi.html** — Visual anatomy guide with inline SVG diagrams. Uses Google Fonts (Lora + DM Sans). Largest file (~54KB) due to extensive SVG illustrations.

## Development

No build, lint, or test commands — open any HTML file directly in a browser.

## Key Patterns

- **Dark mode**: All pages support `prefers-color-scheme: dark` via CSS custom properties (variables defined in `:root` and overridden in a dark media query).
- **Two design systems**: `index.html` and `ghid_ramuri_pomi.html` share a warm/earthy palette (`--bark`, `--leaf`, `--gold`, `--cream` vars). `tabel_taieri_livada.html` and `ghid_taieri_pomi.html` share a neutral palette (`--bg`, `--text`, `--border` vars).
- **Species color coding**: Each fruit species has a consistent badge/dot color across all pages (e.g., mar=green, par=blue, cires=gold, piersic=red, prun=purple).
- **All content is in Romanian** — preserve language and diacritics (ă, â, î, ș, ț) when editing.
- **Inline SVG**: Illustrations are hand-crafted SVG embedded directly in HTML, not external files.
- **favicon.ico** is referenced from all pages via `<link rel="icon" href="favicon.ico">`.