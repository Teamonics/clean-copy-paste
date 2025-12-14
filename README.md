# 📋 Clipboard Cleaner

A single-file, offline HTML tool that cleans up messy copied text from PDFs, emails, Slack, web pages, and more. Runs entirely in your browser — no uploads, no tracking, no server required.

## Why?

Copied text is often messy:
- Hard line wraps from PDFs that break paragraphs
- Inconsistent spacing and extra blank lines
- Curly quotes and fancy dashes that break code/configs
- Invisible characters (zero-width spaces, BOMs)
- Weird bullet formatting from different apps

Cleaning it manually is tedious. This tool fixes common issues in seconds.

## Features

- **Smart paragraph unwrapping** — Joins hard-wrapped lines while preserving intentional breaks
- **List preservation** — Detects and keeps bullet/numbered lists intact
- **Code block detection** — Preserves indented blocks (4+ spaces or tabs)
- **Whitespace normalization** — Collapses multiple spaces, trims trailing whitespace
- **Newline cleanup** — Converts CRLF/CR to LF, collapses excessive blank lines
- **Invisible character removal** — Strips zero-width spaces, BOM, non-breaking spaces
- **Typography conversion** — Straightens curly quotes, converts em/en dashes to hyphens
- **Bullet normalization** — Converts various bullet symbols to standard `- `
- **Duplicate line removal** — Optional deduplication for lists/logs
- **One-click copy** — With clipboard API fallback for older browsers
- **Undo/Redo** — Full history with keyboard shortcuts (Ctrl/Cmd+Z)
- **Download as .txt** — Export cleaned text directly
- **Remembers settings** — Optional localStorage persistence

## Presets

| Preset | Best For |
|--------|----------|
| **📄 Docs** | PDFs, emails, general text. Unwraps paragraphs, preserves lists/code. |
| **📝 Markdown** | Keeps line breaks, normalizes bullets to `- ` |
| **🔤 ASCII** | Code/configs. Straightens all quotes and dashes. |
| **📦 Compact** | Logs/data. Removes duplicates, aggressive cleanup. |

## Usage

1. **Paste** messy text into the input area
2. **Select a preset** or toggle individual options
3. **Click Apply** (or press Ctrl/Cmd+Enter)
4. **Click Copy** to grab the cleaned output

That's it. Paste → Apply → Copy.

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + Enter` | Apply transformations |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Shift + Z` | Redo |

## Installation

### Option 1: Just open it
Download `clipboard-cleaner.html` and double-click to open in any browser. Done.

### Option 2: GitHub Pages (free hosting)

1. Create a new GitHub repository
2. Upload `clipboard-cleaner.html`
3. Go to **Settings → Pages → Source: main branch**
4. Access at `https://YOUR-USERNAME.github.io/REPO-NAME/clipboard-cleaner.html`

### Option 3: Any static host
Upload the single HTML file to Netlify, Vercel, S3, or any web server. No build step required.

## Privacy & Security

This tool is designed for privacy:

- ✅ **100% client-side** — All processing happens in your browser
- ✅ **No uploads** — Your text never leaves your device
- ✅ **No external requests** — Zero network calls at runtime
- ✅ **No tracking** — No analytics, cookies, or telemetry
- ✅ **No account required** — Just open and use
- ✅ **Strict CSP** — Content Security Policy blocks all external connections
- ✅ **Optional storage** — Settings saved to localStorage only if you enable "Remember"

## Technical Details

- **Single HTML file** — ~1000 lines, no dependencies
- **No frameworks** — Vanilla JavaScript, no build tools
- **DOM-safe** — Uses `textContent` and `createElement`, no `innerHTML` injection
- **Accessible** — Keyboard navigable, ARIA labels, focus states, screen reader support
- **Mobile-friendly** — Responsive layout, touch-friendly targets (44×44px minimum)
- **Size limit** — Handles up to ~5MB of text; warns at ~2MB

### Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13.1+
- Edge 80+

## Limitations

- **Plain text only** — No rich text/HTML formatting preserved
- **Heuristic detection** — Paragraph/list detection is best-effort, not perfect
- **No AI** — Doesn't rewrite or summarize, just cleans
- **No OCR** — Can't extract text from images

## Customization

The transformation pipeline runs in this order:

1. Normalize line endings (CRLF/CR → LF)
2. Strip invisible characters
3. Convert tabs to spaces (if enabled)
4. Straighten quotes (if enabled)
5. Straighten dashes (if enabled)
6. Normalize bullets (if enabled)
7. Unwrap hard line breaks (if enabled)
8. Normalize whitespace
9. Collapse excessive newlines
10. Remove duplicate lines (if enabled)

Each step can be toggled independently or selected via presets.

## Contributing

Found a bug or have a suggestion? Open an issue or submit a PR.

Common improvement ideas:
- [ ] Find/replace panel
- [ ] Regex-based custom rules
- [ ] Side-by-side diff view
- [ ] Email/phone redaction
- [ ] Import/export settings as JSON

## License

MIT License — Use freely, modify freely, no warranty.

---

Made for anyone who copies text between tools and is tired of fixing formatting manually.
