# Instaframe

A simple tool I built because I got tired of Instagram cropping my photos in weird ways ya.

You drop an image in, pick a ratio, set a border thickness and color, and download it. That's it. No accounts, no uploads to a server, no watermarks. Everything happens in your browser.

---

## What it does

It takes your image and places it inside a frame that matches whichever Instagram ratio you pick. The important part — **your original image is never touched**. No resizing, no compression, no pixel changes. The tool just builds a canvas around it. The border is extra space, not something that eats into your photo.

When you download, you get the full resolution output. Whatever your image was going in, that's what comes out — just with a clean frame around it.

---

## Ratios

| Ratio | Use case |
|-------|----------|
| **4:5** | Regular feed posts. Most real estate on screen, probably what you want. |
| **1:1** | Square. The classic. |
| **3:4** | Slightly taller feed post. Good for portraits. |
| **9:16** | Reels and Stories. Full vertical. |

---

## How to use it

1. Open `instagram-box-generator.html` in any browser
2. Tap or click the upload zone (or just drag your image onto it)
3. Pick your ratio
4. Drag the border slider until it looks right
5. Pick a color — white and black are the usual suspects, but there are presets for cream, red, navy, sand, blush
6. Hit Download

The file saves as a `.jpg` named with the ratio and exact pixel dimensions so you always know what you're working with.

---

## No dependencies

There's no npm, no build step, no bundler. It's one HTML file. Open it and it works. The only thing it loads externally is a Google Fonts stylesheet for the UI.

---

## Why the image stays untouched

Most tools resize your image to fit the target dimensions. This one doesn't. Instead, it figures out how big the canvas needs to be to fit your image *plus* the border, and then expands that canvas further if needed to match the aspect ratio. Your image sits in the center at its original size.

This matters if you're uploading a high-res photo and don't want Instagram to do any further degrading after you've already gone through the trouble of exporting it properly.

---

## Browser support

Works in any modern browser. Chrome, Firefox, Safari, Edge — all fine. Uses the Canvas API for rendering and `toBlob` for the download, which have been supported everywhere for years.

On mobile it stacks into a single-column layout. The upload zone doubles as the preview.

---

## Known quirks

- If your border is set to 0 and the image is already the exact target ratio, the output will literally be identical to the input. That's correct behavior, not a bug.
- Very large images (like 20MP+ RAW exports) might take a second to render the preview. The download will still be full resolution.
- The hex color input expects a 6-digit hex code with the `#`. If you type without it, it adds one automatically.

---

## Made by

**GRAAAA** — [github.com/graaaa](https://github.com/graaaa)
