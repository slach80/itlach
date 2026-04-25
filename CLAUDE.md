# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Classical piano recruiting portfolio for Isaac Lach (Class of 2031, 7th Grade), modeled after `/home/slach/Projects/nonotib`. Static HTML site tracking Isaac's piano development and conservatory admissions journey.

## Pages

| Page | Purpose |
|------|---------|
| `index.html` | Hero profile, stats, musical journey, recordings, academics, target schools, contact |
| `schools.html` | Filterable conservatory/university program directory |
| `map.html` | Interactive Leaflet.js map of target schools; filters by region and type |
| `scholarships.html` | Talent scholarships, merit aid, competition prizes, planning timeline |
| `competitions.html` | Competition history (todo) and target events to pursue |
| `repertoire.html` | Current, learned, and target pieces by composer |
| `testprep.html` | SAT/ACT comparison, score→scholarship map, roadmap, resources, localStorage score tracker |

## Development

No build step. Edit HTML files directly. All CSS is inline `<style>` blocks in each page — no external stylesheets.

Push to `main` to deploy via GitHub Pages.

## Design System

All pages share the same CSS variables — defined in each page's `:root` block:

| Variable | Value | Use |
|---|---|---|
| `--accent` | `#c9a84c` | Gold — primary accent, buttons, borders |
| `--accent-dark` | `#8a6a1a` | Dark gold — text accents, labels |
| `--ebony` | `#1a1208` | Near-black — hero backgrounds, footer |
| `--bg` | `#f9f6f0` | Warm ivory — main background |
| `--text` | `#1a1208` | Body text |
| `--muted` | `#7a6e5f` | Secondary text, labels |

**Fonts (Google Fonts):**
- `Playfair Display` — display headings, hero name, section titles (serif, elegant)
- `Cormorant Garamond` — body text, descriptions (refined serif)
- `Josefin Sans` — labels, badges, nav links, uppercase UI (geometric sans)

**School type badge colors (consistent across pages):**
- Conservatory: red `#8b3030`
- University: blue `#005090`
- Local/regional: gold `var(--accent-dark)`

## Architecture Notes

- Nav is duplicated across all pages (no shared includes). Edit all 7 files when updating nav.
- Hamburger mobile menu activates at `<960px`.
- Scroll reveal uses `IntersectionObserver` with `.reveal`, `.reveal-d1/d2/d3` stagger classes.
- `map.html` uses Leaflet.js via CDN + CartoDB Voyager tiles. Schools array is embedded in the script block.
- `testprep.html` score tracker persists to `localStorage` under key `isaac_scores`.
- All pages have a fixed `--nav-h: 72px` that page headers use for `padding-top`.

## Profile Data (update as Isaac develops)

- **Student:** Isaac Lach, 7th grade, Walden Middle School, Kansas City MO
- **Instructor:** Eva Peng
- **GPA:** 3.9
- **Class year:** 2031
- Current repertoire, competition results, and recordings are all marked `todo` — update in the relevant HTML sections.
