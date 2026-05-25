# AGENTS.md

Instructions for AI coding agents working on this repository.

## What this repo is

The public engineering site for WitzOps. A static Astro site deployed to
Cloudflare Pages. Content covers infrastructure, automation,
observability, and AI-assisted engineering — written as field notes, not
marketing copy.

## Development commands

```sh
npm install       # install dependencies
npm run dev       # start Astro dev server
npm run build     # production build to ./dist/
npm run preview   # preview production build locally
```

## Critical rules

### Never include private infrastructure details

This is a public repository. Never add:

- IP addresses, internal hostnames, or FQDNs.
- API keys, tokens, passwords, or secrets of any kind.
- Internal network topology or architecture diagrams with real labels.
- Runbook procedures that describe operational steps against live
  infrastructure.
- SSH keys, certificates, or private key material.

If content references real infrastructure, replace specific details
with placeholders (e.g. `[REDACTED]`, `lab-router`, `10.x.x.x`) and flag
it for review.

### Tone and voice

- **Engineering-first**. Write like field notes, not a startup pitch.
- **Practical**. Focus on what was done, why, and what was learned.
- **No exaggerated claims**. Avoid "revolutionary", "game-changing",
  "cutting-edge AI platform" language.
- **No startup buzzwords**. Skip "disrupt", "empower", "unlock", "robust",
  "scalable", "best-in-class".
- **Show, don't market**. Describe real implementations and trade-offs.

### Commit conventions

- Use conventional commits: `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`
- Keep commits focused — one logical change per commit.
- Pull request descriptions follow the template in
  `.github/pull_request_template.md`.

### Code style

- Astro components use `---` frontmatter fences for logic, HTML below.
- CSS is scoped to components using Astro `<style>` tags.
- Global styles live in `BaseLayout.astro` under `<style is:global>`.
- TypeScript strict mode per `tsconfig.json`.
- Site metadata (title, navigation items) lives in `src/data/site.ts`.

### File organization

```
src/
  components/   # reusable Astro components
  data/         # shared constants (site metadata, nav items)
  layouts/      # page layout components
  pages/        # route-level pages and content directories
docs/
  decisions/    # architecture decision records
```

## Before submitting changes

- `npm run build` must succeed.
- No private infrastructure details present.
- Content matches the engineering notebook tone.
- All links resolve to valid pages or sections.
