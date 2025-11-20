# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static single-page website for a tech consulting portfolio. The entire site is contained in a single `index.html` file with embedded CSS and JavaScript. It's deployed on GitHub Pages.

**Key characteristics:**
- Pure HTML/CSS/JavaScript (no build tools required)
- Responsive design with dark theme
- Smooth scroll navigation
- Single file deployment

## Development

### Running the Site Locally

Since this is a static HTML file, you can view it directly in a browser:

```bash
# Open in default browser
open index.html

# Or use a simple HTTP server
python3 -m http.server 8000
# Then navigate to http://localhost:8000
```

### Structure

The `index.html` file contains:
- **Embedded CSS** (lines 11-128): Uses CSS variables for theming. Main theme variables defined in `:root`
- **Navigation** (lines 133-140): Logo and links with smooth scroll anchors
- **Hero section** (lines 142-152): Main headline and CTA
- **Services section** (lines 154-188): Grid layout showcasing Core Engineering, Data Systems, and Applied AI
- **Philosophy section** (lines 190-206): The "Zero to One" approach
- **CTA footer** (lines 208-212): Call-to-action section
- **Footer** (lines 214-217): Copyright with dynamic year
- **Smooth scroll JavaScript** (lines 220-229): Handles anchor link navigation

### Styling

Color scheme is defined via CSS variables in `:root`:
- `--bg-color`: Dark background (#0a0a0a)
- `--text-primary`: Light text (#ededed)
- `--text-secondary`: Muted text (#888888)
- `--accent`: Tech blue (#3b82f6)
- `--glass`: Semi-transparent white (glassmorphism effect)
- `--border`: Subtle borders
- `--font-main`: Inter (primary font)
- `--font-mono`: Space Mono (monospace/accent font)
- `--max-width`: Container width (900px)

To update colors/fonts, modify these variables in the `:root` selector (lines 12-22).

### Making Updates

**Content updates:**
1. Edit text directly in the HTML (sections are clearly labeled with comments)
2. Preserve the markup structure
3. Skill tags are in `.skills-list` divs within `.card` elements

**Styling updates:**
1. Modify CSS variables in `:root` for global changes
2. Media query at line 123 handles mobile responsiveness
3. All component styles are organized by function (Navigation, Hero, Services Grid, etc.)

**Adding new sections:**
1. Follow the existing pattern: wrap in `.section` class with `id` attribute
2. Add navigation link in the `nav` element
3. Use `.grid` and `.card` classes for consistent styling

### Deployment

The site is deployed on GitHub Pages. Changes to `index.html` automatically deploy when pushed to the main branch (as configured in GitHub repository settings).

To verify deployment:
1. Push changes to `main` branch
2. GitHub Actions automatically builds and deploys
3. Site is live at the configured GitHub Pages URL

### External Assets

The site uses:
- **Google Fonts**: Inter and Space Mono (imported via CDN, lines 8-10)
- No other external dependencies or build tools

All fonts are loaded with `preconnect` hints for performance.
