# CLAUDE.md

## Overview

EnneadTabWiki is a static documentation site for EnneadTab tools. It provides knowledge-base articles covering installation, Revit tools, Rhino tools, and CAD tools. Built with plain HTML/CSS (no framework), deployed via GitHub Pages.

## Repository Structure

```
EnneadTabWiki/
  index.html             # Landing page with video background
  installation.html      # Installation guide
  revit.html             # Revit tools documentation
  rhino.html             # Rhino tools documentation
  CAD.html               # CAD tools documentation
  style.css              # Global styles
  assets/                # Images, icons, and videos
```

## Development

No build step. Open any `.html` file in a browser to preview.

All pages share `style.css` for consistent styling. Chart.js is loaded via CDN for any data visualizations.

## Architecture

- **Pure static site**: HTML + CSS + vanilla JavaScript
- **Assets**: Tool icons follow the naming convention `_{platform}_{extension}_{tab}_{panel}_{tool}_icon.png`
- **Video**: Background video on landing page (`assets/background-video.mp4`)
- **No dependencies**: No package.json, no build tools

## Deployment

Hosted on GitHub Pages from the repository root.
