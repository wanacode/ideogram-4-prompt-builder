# Ideogram 4 Prompt Builder

A single-page tool for visually composing structured **JSON prompts** for Ideogram 4 image generation. Build up a high-level description, background, and positioned layout boxes, then copy out a ready-to-use JSON prompt.

## 📖 Documentation

For the full JSON prompting spec and field reference, see the official docs:

**→ [Ideogram 4 JSON Prompting Guide](https://github.com/ideogram-oss/ideogram4/blob/main/docs/prompting.md)**

## Features

- **Prompt** — write the high-level description and background, the core of every prompt.
- **JSON** — view and copy the generated JSON prompt (compact or pretty).
- **Layout** — draw and position elements visually as layout boxes.
- **Settings** — composition guide and generation options.
- **Presets** — load demo presets to see complete example prompts.

## Development

Styles are built with [Tailwind CSS v4](https://tailwindcss.com) via the standalone CLI. The local workflow uses [pnpm](https://pnpm.io):

```bash
pnpm install        # install dev dependencies
pnpm dev            # watch src/input.css → dist/output.css and rebuild on change
pnpm build          # one-off minified production build
```

Tailwind config lives in `src/input.css` (v4 is CSS-first — `@theme`, `@source`); the compiled stylesheet is written to `dist/output.css`, which `index.html` links to.

> **Note:** `dist/output.css` is generated (gitignored). Run `pnpm build` (or `pnpm dev`) at least once before opening `index.html`, or the page will be unstyled.

## Deployment (Netlify)

The site deploys from Git. `netlify.toml` configures everything:

- **Build command:** `pnpm build`
- **Publish directory:** `.` (repo root)
- **Node:** 20

pnpm is auto-detected from `pnpm-lock.yaml`, so no Netlify dashboard changes are needed.
