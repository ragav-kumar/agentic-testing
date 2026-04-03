# Copilot Instructions

## Repository

`agentic-testing` is a static brochure website for **LymeAlert** — an at-home tick testing kit for early Lyme disease detection. The site is published via GitHub Pages.

## Architecture

Single-page static site — no build step, no framework, no package.json.

- `index.html` — entire site in one file (nav, hero, how-it-works, lyme disease facts, product, signup CTA, FAQ, footer)
- `.github/workflows/deploy.yml` — GitHub Actions workflow that deploys to GitHub Pages on every push to `main`

## Styling & Scripts

- **Tailwind CSS** loaded via CDN (`https://cdn.tailwindcss.com`) with a custom `tailwind.config` inline in `<script>`
- Custom color tokens: `forest`, `moss`, `bark`, `cream`, `alert` — defined in the inline Tailwind config
- Google Fonts (`Inter`, `Playfair Display`) loaded via `<link>` in `<head>`
- All JavaScript is vanilla, inline at the bottom of `index.html` (scroll reveal via `IntersectionObserver`, FAQ accordion, sticky nav, mobile menu, form submit)

## Deployment

GitHub Actions workflow (`.github/workflows/deploy.yml`) uses the official Pages actions:
`actions/configure-pages` → `actions/upload-pages-artifact` → `actions/deploy-pages`

To enable Pages: go to **Settings → Pages → Source → GitHub Actions** in the repository.

## Git LFS

Large binary files (images, videos) should be tracked via Git LFS.
