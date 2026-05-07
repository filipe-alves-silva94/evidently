# Evidently.

> A visual investigation board for tasks, ideas and connections — no server, no login, no columns.

---

## What is it?

**Evidently** is a single-file, offline-first kanban board inspired by detective investigation walls. Instead of fixed columns, you place cards freely on a cork board, connect them with colored strings, group them into colored zones, and navigate the whole thing with zoom and pan.

Everything runs in a single `.html` file. No build step, no dependencies, no server. Open it in a browser and start pinning.

---

## Features

### Cards
- **Note cards** — title, description, checklist with progress bar, due date with overdue alert, and tag
- **Photo cards** — attach images via URL or local file upload, with caption
- **Status badge** — click to cycle between `A FAZER → FAZENDO → FEITO ✓`
- **5 tags** — `work`, `pessoal`, `urgente`, `ideia`, `meeting`
- **4 pin colors** — red, blue, yellow, green
- **4 card variants** — default, aged, note (yellow), red tint
- **Drag freely** anywhere on the board
- **Double-click** to edit, **single-click** on badge to cycle status

### Connections (String)
- Click a card's pin to enter connection mode
- Click a second card to draw a curved string between them
- **8 string colors** configurable per card
- **Typed relations** — label strings as: `bloqueia`, `depende de`, `relacionado`, `referência`
- Labels appear inline over the string midpoint

### Zones
- Create colored background areas to group cards visually
- **Drag** by the header, **resize** from the bottom-right corner
- **Double-click** the zone name to rename inline
- 6 preset color themes

### Navigation
- **Scroll** to zoom in/out, centered on cursor
- **Middle mouse button** to pan the board
- **Pinch-to-zoom** and **1-finger pan** on touch devices
- **Minimap** — appears in the top-right corner during pan, showing all cards at a glance
- **Zoom indicator** — click the `%` badge to reset the view

### Multi-select
- **Drag on empty board** area to draw a lasso selection
- **Shift+click** to add/remove cards from selection
- **Drag any selected card** to move the whole group

### Focus Mode
- Click **"focar"** on any card to highlight it and its direct connections
- All unrelated cards and strings fade to near-invisible
- Click a dimmed card or the board background to exit, or press `Esc`

### Search
- Search bar in the header filters cards by title, description, tag, caption and checklist items
- Supports multiple terms separated by spaces
- Non-matching cards dim; matching cards stay highlighted with a result count
- Press `Esc` or click outside to clear

### Templates
- Select a card, then click **📋 Templates** in the toolbar
- Save its layout (title, description, checklist structure, tag, style) as a reusable template
- Templates persist across sessions in `localStorage`
- Instantiate a template card directly into the center of the current view

### Multiple Boards
- Create as many boards as you need using the `+` tab button
- Each board has its own cards, zones and connections
- The active board is reflected in the URL hash (`#boardId`) for bookmarking
- Browser back/forward navigate between boards

### Board Properties (⚙)
- Rename the active board
- **Export** — saves all boards as a single `.invboard` file (JSON)
- **Import** — load an `.invboard` file; choose to add as new boards, replace the current board, or merge content
- **Save as PNG** — captures the board as a high-resolution image
- Reset session (clears all data)

### History
- **Ctrl+Z** — undo (up to 60 levels per board)
- **Ctrl+Shift+Z** or **Ctrl+Y** — redo
- History is independent per board and clears on board switch
- Card position drags do not pollute the undo stack

### Mobile & Touch
- Full touch support: drag cards, double-tap to edit, pinch to zoom, 1-finger pan
- Floating **＋** action button (FAB) expands into add options
- All modals open as bottom sheets on small screens
- iOS safe-area insets respected

---

## Getting Started

No installation required.

1. Download `evidently.html`
2. Open it in any modern browser
3. Start adding cards

```
open evidently.html
```

That's it.

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Scroll` | Zoom in / out |
| `Middle mouse` | Pan the board |
| `Double-click card` | Edit card |
| `Click pin` | Start / finish connection |
| `Ctrl+Z` | Undo |
| `Ctrl+Shift+Z` | Redo |
| `Ctrl+Y` | Redo |
| `Esc` | Cancel connect / close modal / exit focus |
| `Shift+click` | Add card to selection |

---

## File Format

Boards are exported as `.invboard` files — plain JSON with a version field. You can inspect or edit them manually.

```json
{
  "version": 1,
  "exported": "2025-01-01T00:00:00.000Z",
  "boards": [{ "id": "abc123", "name": "My Board" }],
  "cards":  { "abc123": [ ... ] },
  "conns":  { "abc123": [ ... ] },
  "zones":  { "abc123": [ ... ] }
}
```

Images uploaded locally are stored as base64 inside the card object. This makes the file self-contained but can grow large — export regularly to avoid hitting `localStorage` limits.

---

## Data & Privacy

- **Everything stays on your device.** No data is ever sent to a server.
- Cards, zones and connections are saved automatically to `localStorage`.
- Export `.invboard` files for backups or to share boards with others.
- Clearing browser storage will erase your data — always keep an exported backup.

---

## Browser Support

Works in any modern browser that supports ES2020+:

| Browser | Status |
|---|---|
| Chrome / Edge 90+ | ✓ Full support |
| Firefox 90+ | ✓ Full support |
| Safari 15+ | ✓ Full support |
| Mobile Chrome / Safari | ✓ Full touch support |

The PNG export feature requires access to `esm.sh` (CDN) to load `html2canvas`. If your network blocks external CDNs, the export will fall back to a prompt suggesting a system screenshot instead.

---

## Roadmap ideas

- [ ] Collaborative real-time editing (WebSockets / CRDT)
- [ ] Activity log per card (created by, edited at, comments)
- [ ] Typed relation filtering (show only cards that "bloqueia" others)
- [ ] Dark mode / alternate cork themes
- [ ] Card color customization beyond the 4 variants
- [ ] Keyboard-driven card creation

---

## License

MIT — do whatever you want with it.

---

<p align="center">
  <strong>Evidently.</strong> — connect the dots.
</p>
