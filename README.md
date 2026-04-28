# Moodboard

A self-contained, no-login collaborative moodboard — like Miro meets PureRef. One HTML file. Host it on GitHub Pages and share the URL.

![Moodboard](https://img.shields.io/badge/deploy-GitHub%20Pages-black?style=flat-square) ![Zero dependencies](https://img.shields.io/badge/dependencies-zero-c8f261?style=flat-square) ![Single file](https://img.shields.io/badge/single-file-c8f261?style=flat-square)

---

## Deploy in 60 seconds

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to **Deploy from branch → `main` → `/ (root)`**
4. Visit `https://yourusername.github.io/moodboard/`

That's it. No build step, no npm, no server.

---

## Features

### Canvas
- Infinite pan & zoom canvas with dot-grid background
- Smooth pan momentum when scrolling

### Input methods
| Action | How |
|--------|-----|
| Add image | Drag & drop files · Paste from clipboard · 🖼 button |
| Add text | Press `T` or click toolbar, then click canvas |
| Add sticky note | Press `S`, pick a color, click canvas |
| Add link card | Press `L` or click 🔗 — auto-fetches OG title & thumbnail |

### Trackpad (MacBook)
| Gesture | Action |
|---------|--------|
| Two-finger scroll | Pan canvas |
| Pinch | Zoom in/out |

### Mouse
| Input | Action |
|-------|--------|
| Scroll wheel | Zoom centered on cursor |
| Drag canvas | Pan (in pan mode) |
| Ctrl + scroll | Zoom |

### Nodes
- Drag to move freely anywhere on the board
- Resize with the corner handle (visible when selected)
- Delete with the `×` button or `Delete` / `Backspace` key
- Text and sticky notes are inline-editable

### Sharing
- Click **⛓ Share** to generate a URL with the full board state encoded in the hash
- Anyone with the link can open and edit — no login required
- Board auto-saves to `localStorage` on the same device

---

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `Space` (hold) | Pan mode |
| `V` | Select mode |
| `T` | Add text |
| `S` | Add sticky |
| `I` | Add image |
| `L` | Add link |
| `Del` / `Backspace` | Delete selected node |
| `F` | Fit all nodes in view |
| `+` / `-` | Zoom in / out |
| `0` | Reset zoom to 100% |
| `Escape` | Deselect |

---

## How sharing works

When you click **Share**, the entire board state (node positions, content, viewport) is JSON-serialized, base64-encoded, and written into the URL hash:

```
https://yourusername.github.io/moodboard/#board=eyJ0aXRsZSI6...
```

Anyone opening that URL gets the exact same board, fully editable. No server, no database.

> **Note on large boards:** Images are stored as base64 data URIs. Very large boards (many high-res images) may exceed URL length limits. In that case, use the board on a single device via `localStorage`, or host images externally and add them as URLs.

---

## Repo structure

```
/
├── index.html   ← The entire app
└── README.md
```

---

## Local use (no hosting needed)

Just open `index.html` directly in any modern browser. Everything works offline except:
- Link card thumbnail fetching (requires internet + CORS proxy)
- Google Fonts (falls back gracefully to system fonts)

---

## Customization

The app uses CSS variables at the top of `index.html` — change colors, fonts, or sizes in the `:root` block:

```css
:root {
  --bg: #0e0e0e;
  --accent: #c8f261;
  /* ... */
}
```

---

## License

MIT — do whatever you want with it.
