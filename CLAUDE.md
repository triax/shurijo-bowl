# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website project for the "第3回 首里城ボウル" (3rd Shurijo Bowl), an American football event featuring TRIAX vs Ryukyu Guardian Lions scheduled for June 29, 2025 in Okinawa, Japan.

## Project Structure

- `/2025/` - Main event page directory
  - `index.html` - Event landing page with dynamic player data loading
  - `2025.css` - Event-specific styling with animations
  - `README.md` - Event information and data sources
- `/index.css` - Global styles shared across the project

## Key Features

1. **Dynamic Player Data Loading**: The site fetches player information from a Google Sheets CSV endpoint
2. **Key Visual Integration**: Displays event poster from Google Drive
3. **Interactive UI**: Uses AOS (Animate On Scroll), jQuery, and Tailwind CSS for animations
4. **Responsive Design**: Mobile-first approach with breakpoints for various devices

## Development Commands

This is a static HTML/CSS/JS project with no build process. To develop:

```bash
# Serve the site locally (use any static server)
python3 -m http.server 8000
# or
npx serve .
```

## External Dependencies

The project uses CDN-hosted libraries:
- Tailwind CSS for utility styling
- jQuery for DOM manipulation
- AOS for scroll animations
- Font Awesome for icons
- Google Fonts (Bebas Neue, Noto Sans JP)

## Data Sources

- Player roster: Google Sheets CSV export at `https://docs.google.com/spreadsheets/d/1pBskF8oCg3HrdWtv0xACeWDfe7_mZZ8-2a8gncHRhjA/gviz/tq?tqx=out:csv`
- Key visual image: Google Drive file ID `1fuqRf0ehzLjTGAzmzui3orfc8zLkHS8I` (accessed via `https://drive.google.com/open?id=1fuqRf0ehzLjTGAzmzui3orfc8zLkHS8I`)