# hshs landing page

Public URL: https://broccolito.github.io/hshs/

This folder contains the GitHub Pages website: two before-and-after sliders, simple fade-in animations and an installation prompt users can copy into Codex. It uses plain HTML, CSS and JavaScript, with no build step, tracking, cookies or remote fonts.

## Local preview

From the repository root:

```sh
python3 -m http.server 8765 --directory landing
```

Open http://localhost:8765. The page uses relative asset paths so it also works at the GitHub Pages `/hshs/` subpath. Clipboard copy needs HTTPS or localhost; an accessible text-selection fallback is provided.

## Images

The examples feature entirely fictional East Asian adults. Each original was generated as a natural portrait with a few everyday skin or grooming details, then edited separately using hshs. Real-person references informed only broad setting, framing and styling; no screenshot or reference face is included. The two pairs show a seated cafe portrait and a selfie taken in a car. The page identifies them as AI-generated examples. They do not show customers, and the edits do not preserve every pixel. No user's private portrait is published.

`assets/` contains four JPEG display assets and the corresponding generation/edit prompts. Pairs share dimensions and framing. Only format conversion/compression was applied for web delivery, without additional visual retouching. Generative editing can change fine texture outside the requested area, even when the overall photo looks similar.

## Interaction and accessibility

The comparisons use native range controls: drag or tap, or focus them with Tab and use arrow keys, Home and End. Left reveals the edited image; right reveals the original. Labels identify each side. The controls expose their values to assistive technology. Animations respect reduced-motion preferences; content is visible if JavaScript is unavailable.

## Deployment

`.github/workflows/landing.yml` publishes this directory to GitHub Pages on pushes to `main` affecting this folder. Pages must use GitHub Actions as its source. The workflow requests only content read, Pages write and deployment identity permissions. Update the repository About website field when changing the public URL.

## Verify changes

- Check both comparisons at 0%, 50% and 100%; images must keep their geometry.
- Confirm installation prompt copy and its fallback, GitHub/ZIP links, and keyboard controls.
- Check mobile single-column and desktop two-column layouts, readable text and reduced motion.
- Check that assets load through the deployed `/hshs/` path.
- Keep fictional-person disclosure visible and never exaggerate the originals' imperfections.
