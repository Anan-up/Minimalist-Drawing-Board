[English](README.md) | [简体中文](README_Simplified_Chinese.md) | [繁體中文](README_Classical_Chinese.md)

# Minimal Drawing Board

A **zero-dependency, single-file** web drawing board. Double-click `index.html` to use it in your browser — no installation, no internet connection, no build step required.

Clean minimalist white style, supporting various brush tools, layers, image and text object editing, customizable canvas, and multi-format export.

---

## Quick Start

| Method | Action |
| ------ | ------ |
| Single file | Simply double-click `index.html` and open it with any modern browser |
| Zip package | Unzip `MinimalDrawingBoard.zip` and open the `index.html` inside |

> Environment requirements: Modern browsers such as Chrome / Edge / Firefox / Safari (Canvas 2D support required).

---

## Features

### Brush Tools

* **Select / Move**: Select text and image objects, supporting move, scale, and rotate
* **Pen**, **Brush (soft edge)**, **Pencil**, **Eraser**
* **Line**, **Rectangle**, **Ellipse**, **Arrow**
* **Text**

### Layers

* Create / delete layers, show / hide
* Drag to reorder layers
* Real-time layer thumbnail preview
* Double-click layer name to rename
* Text / image objects within a layer are listed as labels; click to select

### Text and Image Objects (Vector, independent of the pixel layer)

* Text as independent objects: **move**, **scale**, **change color**, **rotate**, double-click to re-edit
* Image insertion: click the toolbar button, drag a file onto the canvas, or right-click "Insert Image"
* Control points appear when an object is selected: scale from four corners/edges, rotate via the top dot

### Canvas

* **Custom size**, with common presets: 800×600, 1024×768, 1280×720, 1920×1080, 1080×1080, A4, A3, phone portrait
* **Custom background color** (supports pure white, any color, transparent checkerboard)
* Scroll-wheel zoom, space/middle-button drag to pan, double-click empty area to reset view
* Real-time zoom ratio shown at the bottom

### Export

* PNG (transparent background / white background / current background color)
* JPEG (white background)
* WebP (transparent background)
* Copy to clipboard

### Other

* **Undo / Redo** (up to 40 steps of history)
* **Right-click menu**: insert image, add text, undo/redo, create/delete/clear layers, fit to window, quick export
* Low-opacity ink **does not darken when overlapped** (the whole stroke is composited at once)

---

## Keyboard Shortcuts

| Key | Function |
| --- | -------- |
| `V` | Select / Move |
| `P` | Pen |
| `B` | Brush (soft edge) |
| `C` | Pencil |
| `E` | Eraser |
| `L` | Line |
| `R` | Rectangle |
| `O` | Ellipse |
| `A` | Arrow |
| `T` | Text |
| `I` | Insert image |
| `\[` / `]` | Decrease / increase brush size |
| `Space` + drag | Pan canvas |
| Middle-button drag | Pan canvas |
| Scroll wheel | Zoom canvas |
| `Ctrl / Cmd + Z` | Undo |
| `Ctrl / Cmd + Y` or `Shift + Ctrl/Cmd + Z` | Redo |
| `Ctrl / Cmd + 0` | Reset view |
| `Delete` / `Backspace` | Delete selected object |
| `Esc` | Close right-click menu / cancel text editing |

---

## Usage Tips

* **Insert image**: Use the image button on the toolbar, drag an image onto the canvas, or right-click on the canvas and choose "Insert Image".
* **Edit text**: Click with the text tool on the canvas to input; double-click existing text to re-edit (Enter to confirm).
* **Precise object adjustment**: Switch to the "Select / Move" tool, click the object then drag control points to scale, drag the top dot to rotate; a "Rotate" slider appears in the toolbar when selected.
* **Right-click menu**: Right-click in the canvas area to bring it up; when an object is selected, "Copy" and "Delete" also appear.

---

## Technical Notes

* **Single-file implementation**: HTML + CSS + native JavaScript, all inlined, no third-party dependencies.
* **Pixel layer separated from vector objects**: Brush strokes are drawn to the layer's pixel canvas; text and images are stored as independent vector objects, allowing lossless scaling and rotation.
* **Document / viewport decoupling**: Document size is decoupled from the display viewport; zoom and pan are achieved through the `view = {zoom, x, y}` transform, and all pointer coordinates are inversely mapped back to the document coordinate system.
* **History snapshots**: Undo/redo serializes snapshots of layers (including pixel data and vector object properties).

```
index.html      # The application itself (single file)
README.md       # This documentation
```

Browser compatibility: Chrome 90+ / Edge 90+ / Firefox 88+ / Safari 14+.

---

## Screenshots

![Screenshots](Drawing-board.png)

---

## License

[MIT](LICENSE)
