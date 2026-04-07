# Frontend Slides Pro

A Claude Code skill for creating zero-dependency, animation-rich HTML presentations that run entirely in the browser. Pro edition adds advanced inline editing with image management and reliable large-file storage.

## Features

### Presentation Generation
- **12 curated visual presets** — Bold Signal, Electric Studio, Swiss Modern, Dark Botanical, and more. No generic "AI slop" aesthetics
- **Single HTML file output** — All CSS/JS inline, no npm, no build tools, no dependencies
- **Viewport-perfect slides** — Every slide fits exactly in 100vh with responsive `clamp()` scaling
- **Rich animations** — Scroll-triggered reveals, staggered entrances, parallax effects, particle backgrounds
- **PPT/PPTX conversion** — Extract content from PowerPoint and convert to styled HTML
- **Style discovery** — Generates 3 visual previews so you pick by seeing, not guessing

### Pro Inline Editor (browser-based)
- **Text editing** — Click any text to edit, press `E` to toggle edit mode, `Ctrl+S` to save
- **Image upload** — Drag-and-drop or click to upload, with automatic client-side compression
- **Image placement** — Add images below text, or to the left/right side (creates responsive two-column layout)
- **PNG transparency** — PNG/WebP/GIF preserve alpha channel; only JPEG gets compressed
- **Delete placeholders** — Remove image areas with one click; layout rows auto-unwrap back to normal
- **Add/delete slides** — Insert new slides or remove existing ones in-browser
- **Image resize & move** — Drag handles to resize; drag to reorder within a slide

### Pro Storage
- **IndexedDB fallback** — Presentations with embedded images easily exceed localStorage's 5MB limit. Pro automatically falls back to IndexedDB (supports hundreds of MB)
- **Save status feedback** — Visual confirmation on save; red warning if save fails
- **Version-keyed cache** — Prevents stale data when HTML structure changes

### Share & Export
- **Deploy to Vercel** — One command to get a live URL that works on any device
- **Export to PDF** — Headless browser captures each slide at 1920x1080, combines into PDF
- **Compact mode** — Export at 1280x720 for 50-70% smaller PDF files

## Installation

### Via Claude Code CLI

```bash
claude install-skill https://github.com/Pineconezky/frontend-slides-pro
```

### Manual Installation

```bash
git clone https://github.com/Pineconezky/frontend-slides-pro.git ~/.claude/skills/frontend-slides-pro
```

## Usage

The skill activates automatically when you ask Claude Code to create a presentation. Examples:

```
# Create a new presentation
"Make a 15-slide presentation about AI in e-commerce"

# Convert from PowerPoint
"Convert my-deck.pptx to an HTML presentation"

# Enhance an existing one
"Add images and improve the styling of presentation.html"

# Export
"Export this presentation to PDF"
"Deploy this to a live URL"
```

### Keyboard Shortcuts (in browser)

| Key | Action |
|-----|--------|
| `E` | Toggle edit mode |
| `Ctrl+S` | Save changes |
| `←` `→` `↑` `↓` | Navigate slides |
| `Space` | Next slide |

### Edit Mode Tools

| Button | Function |
|--------|----------|
| **+ Insert slide** | Add a new slide after current |
| **Add image ⬇⬅➡** | Add image area below, left, or right of text |
| **- Delete slide** | Remove current slide |
| 🗑 (on placeholder) | Delete image area |
| × (on image) | Remove uploaded image |

## File Structure

```
frontend-slides-pro/
├── SKILL.md                 # Main skill definition & workflow
├── html-template.md         # HTML architecture & Pro editing system
├── STYLE_PRESETS.md         # 12 visual presets with colors & fonts
├── animation-patterns.md    # Animation reference & effect-to-feeling guide
├── viewport-base.css        # Mandatory responsive CSS for every presentation
└── scripts/
    ├── deploy.sh            # Deploy to Vercel
    ├── export-pdf.sh        # Export to PDF via Playwright
    └── extract-pptx.py      # PowerPoint content extraction
```

## Style Presets

| Preset | Vibe | Theme |
|--------|------|-------|
| Bold Signal | Confident, high-impact | Dark |
| Electric Studio | Clean, professional | Dark |
| Creative Voltage | Energetic, retro-modern | Dark |
| Dark Botanical | Elegant, sophisticated | Dark |
| Notebook Tabs | Editorial, tactile | Light |
| Pastel Geometry | Friendly, approachable | Light |
| Split Pastel | Playful, creative | Light |
| Vintage Editorial | Witty, personality-driven | Light |
| Neon Cyber | Futuristic, techy | Dark |
| Terminal Green | Developer, hacker | Dark |
| Swiss Modern | Clean, Bauhaus-inspired | Light |
| Paper & Ink | Literary, thoughtful | Light |

## Requirements

- **Claude Code** — The CLI tool from Anthropic
- **Node.js** — Required for PDF export (Playwright) and Vercel deploy
- **Python 3 + Pillow** — Optional, for PPT conversion and server-side image compression

## License

MIT
