# hshs landing page

Public URL: https://broccolito.github.io/hshs/

A minimal, static page with two before/after image sliders, restrained reveal animation and a copyable Codex installation prompt. No framework, tracking, cookies, remote fonts or build dependencies. GitHub Pages is the requested host; this folder is the complete publishable site.

## Local preview

From the repository root:

```sh
python3 -m http.server 8765 --directory landing
```

Open http://localhost:8765. The page uses relative asset paths so it also works at the GitHub Pages `/hshs/` subpath. Clipboard copy needs HTTPS or localhost; an accessible text-selection fallback is provided.

## Images

The examples feature entirely fictional East Asian adults. Each original was independently generated as an already appealing, natural portrait with modest visible imperfections, then actually edited with hshs guidance. Real-person references informed only broad setting, framing and styling; no screenshot or reference face is included. The replacement pairs use a seated cafe portrait and a car-seat selfie. They are illustrative AI-generated demonstrations, not photographs of customers or evidence of guaranteed pixel preservation. No user's private portrait is published.

`assets/` contains four JPEG display assets and the corresponding generation/edit prompts. Pairs share dimensions and framing. Only format conversion/compression was applied for web delivery, without additional visual retouching. Actual edits may also regenerate fine texture outside the target region; the public page labels the demonstrations accordingly.

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
