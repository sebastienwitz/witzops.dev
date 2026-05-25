# CLAUDE.md

## Project

**witzops.dev** — public engineering notebook for WitzOps. Static Astro 6
site deployed to Cloudflare Pages. Covers infrastructure, automation,
observability, and AI-assisted engineering.

## Commands

```sh
npm install       # install dependencies
npm run dev       # start dev server (localhost:4321)
npm run build     # production build to ./dist/
npm run preview   # preview production build
```

## Security: never leak private details

This is public. Never commit:

- IP addresses, hostnames, FQDNs, internal URLs.
- Secrets, tokens, keys, passwords, certificates.
- Operational runbook procedures against live infrastructure.
- Network topology with real labels.

Use placeholders for any real infrastructure details that appear in
content. Flag anything questionable for review.

## Tone

- Engineering field notes, not marketing.
- Practical, descriptive, trade-off aware.
- No startup buzzwords ("revolutionary", "game-changing", "robust").
- No inflated claims about AI capabilities.

## Code conventions

- Astro `.astro` files: logic in `---` fences, markup below.
- Scoped `<style>` per component. Global styles in `BaseLayout.astro`.
- TypeScript strict mode.
- Site constants in `src/data/site.ts`.
- Conventional commits: `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`.

## Architecture

```
src/components/   # Header, Footer, Callout, ProjectCard, TagList, ArticleCard
src/data/         # site.ts (title, tagline, navigation)
src/layouts/      # BaseLayout.astro (shell + global CSS)
src/pages/        # index, about, architecture, blog, lab-stack, projects, 404
```

Static output mode. No SSR, no API routes, no runtime database.

## Before PR

- `npm run build` passes.
- No private infrastructure details.
- Engineering-notebook tone maintained.
