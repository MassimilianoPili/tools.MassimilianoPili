# tools.MassimilianoPili

Browser-based developer utilities. No frameworks, no build step. Live at [tools.massimilianopili.com](https://tools.massimilianopili.com).

## Development

No build system. Edit HTML/CSS/JS directly and refresh the browser.

```bash
# Run locally
python -m http.server 8000
# Open http://localhost:8000
```

## Project Structure

```
/                    # Landing page (index.html)
├── css/
│   └── common.css   # Shared styles across all tools
├── mongo/           # MongoDB ↔ Spring @Aggregation bidirectional converter
│   ├── index.html   # Stable version
│   ├── beta/        # Beta versions
│   └── legacy/      # Legacy versions (v0, v1)
├── prettifier/      # JSON & cURL prettifier with syntax highlighting
├── base64/          # Base64 encoder/decoder with file type detection
└── jwt/             # JWT decoder & editor
```

## Key Patterns

- **Self-contained pages**: Each tool is a directory with its own `index.html`. CSS and JS are inline.
- **Shared styles**: `css/common.css` provides base theming (dark mode, typography, layout).
- **Versioning**: Mongo tool maintains `legacy/` and `beta/` subdirectories for backwards compatibility.
- **No dependencies**: Pure HTML5, CSS3, vanilla JavaScript.
- **GitHub Pages**: Deployed via CNAME record (`tools.massimilianopili.com`).

## Conventions

- Root-relative paths between tools
- Dark mode via `prefers-color-scheme` media query
- Each tool is independent — no shared state or JS modules
