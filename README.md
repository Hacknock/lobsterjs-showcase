# lobster.js Showcase

A wiki-style showcase site for [lobster.js](https://github.com/Hacknock/lobsterjs) — an extended Markdown parser that renders rich, structured web pages directly in the browser.

**[View the Showcase →](https://hacknock.github.io/lobsterjs-showcase/)**

---

## What's inside

| Page | What it demonstrates |
| :--- | :--- |
| Introduction | Quick start, API overview, CSS class reference |
| Tables | Standard tables, alignment, cell merging, silent layout grids |
| Warp / Multi-column | `:::warp` blocks, 2-col and 3-col layouts |
| Images | Image sizing (`=Wx` / `=WxH`), image+text layout, image grid |
| Footnotes | Reference footnotes and inline footnotes |
| Code Blocks | Fenced blocks, filename annotation, Prism.js / highlight.js integration |
| Details / Collapsible | `:::details` blocks with rich content inside |

## Structure

```
index.html       ← SPA entry point (?page= routing)
style.css        ← Wiki layout + lbs-* element styles
nav.md           ← Sidebar navigation (loaded once)
content/
  intro.md
  example-table.md
  example-warp.md
  example-image.md
  example-footnotes.md
  example-code.md
  example-details.md
images/
  sample-wide.png
  sample-square.png
```

## How it works

The site is a single `index.html` with no build step:

- `nav.md` is loaded once into the sidebar via `loadMarkdown`
- Page content is loaded dynamically based on the `?page=` query parameter
- Navigation uses `history.pushState` — back/forward buttons work
- lobster.js is loaded from CDN: `https://hacknock.github.io/lobsterjs/lobster.js`

## License

[MIT](./LICENSE) © 2025 Hacknock
