# emoji-download

A single-file browser tool that renders any emoji as a high-resolution PNG and downloads it as a favicon.

## What it does

Type or paste an emoji into the input field, see a live preview, then click **Download favicon.png** to save a 1024×1024 PNG of that emoji — centered and pixel-perfect — named `favicon-<emoji>.png`.

It uses the browser's `Intl.Segmenter` API to correctly handle multi-codepoint emoji (e.g. flags, skin tones, ZWJ sequences) and the Canvas 2D API to measure and center the glyph precisely before export.

## Usage

Open `index.html` in any modern browser. No build step, no dependencies, no server required.

- **Mac emoji picker**: `Ctrl + Cmd + Space`
- **Windows emoji picker**: `Win + .`

## Use cases

- Generate a favicon from an emoji for a side project or prototype
- Quickly export a clean emoji image for use in design tools, presentations, or docs

## How it works

The emoji is drawn at 820px on a 1024×1024 canvas using `ctx.measureText` bounding-box metrics to center it precisely. The canvas is exported via `toDataURL('image/png')` and triggered as a download.
