# PDF Cleaver

A simple, privacy-first PDF cropping tool that runs entirely in your browser — no uploads, no servers, no accounts.

![PDF Cleaver screenshot](https://raw.githubusercontent.com/vhoudoverdov/pdf-cleaver/main/screenshot.png)

## Features

- **Drag & drop or browse** to open any PDF
- **Rectangle selection** — click and drag to define the crop area
- **Page navigation** — crop a single page or apply the same crop to all pages
- **Zoom controls** — zoom in/out or fit the page to the window
- **Instant download** — saves as `<original-name>_cropped.pdf`
- **100% offline after first load** — your files never leave your device

## Usage

1. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari)
2. Drop a PDF onto the page or click **Browse PDF**
3. Click and drag a rectangle over the area you want to keep
4. Choose **This page only** or **All pages** in the toolbar
5. Click **Crop & Save** — a native Save As dialog opens so you can choose exactly where to save

### Keyboard shortcuts

| Key | Action |
|-----|--------|
| `←` / `→` | Previous / next page |
| `+` / `-` | Zoom in / out |
| `Escape` | Clear selection |
| `Enter` | Crop & Save |

## How it works

PDF rendering is handled by [PDF.js](https://mozilla.github.io/pdf.js/) and the cropped output is written by [pdf-lib](https://pdf-lib.js.org/). The crop is applied as a **PDF crop box** — the standard PDF mechanism — which means the operation is lossless and reversible in any PDF editor. No pixel re-rasterization occurs.

## Privacy

This tool processes everything locally in your browser using the [File API](https://developer.mozilla.org/en-US/docs/Web/API/File). The only outbound network requests are:

- Loading [Inter](https://fonts.google.com/specimen/Inter) from Google Fonts (cosmetic only)
- Loading PDF.js and pdf-lib from [cdnjs](https://cdnjs.com/) (Cloudflare)

No PDF content or metadata is ever transmitted anywhere.

## Dependencies

All dependencies are loaded from cdnjs with pinned versions and Subresource Integrity (SRI) hashes.

| Library | Version | Purpose |
|---------|---------|---------|
| [PDF.js](https://mozilla.github.io/pdf.js/) | 3.11.174 | Render PDF pages to canvas |
| [pdf-lib](https://pdf-lib.js.org/) | 1.17.1 | Write the crop box to the output PDF |

## License

[MIT](LICENSE)
