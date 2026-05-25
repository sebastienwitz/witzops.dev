# Agent brief

A concise briefing for AI agents and contributors working on
witzops.dev.

## What we're building

A public-facing engineering notebook. Think of it as infrastructure
field notes that happen to be readable by other engineers.

The site translates private operations work into reusable public
content: architecture decisions, tool evaluations, implementation
patterns, and lessons from running real infrastructure.

## What we're not building

- A marketing site.
- A startup landing page.
- A SaaS product.
- A personal brand vehicle.
- A generic AI/tech blog.

## Architecture at a glance

- **Astro 6** static site generator, no SSR.
- **Cloudflare Pages** for hosting and CDN.
- **GitHub Actions** for CI (build verification only).
- Plain CSS (scoped per component, global in BaseLayout).
- No framework runtime on the client. No React/Vue/Svelte in the
  production bundle. Astro components render to static HTML.

## Content categories

1. **Architecture patterns** — How systems are structured and why.
2. **Tool evaluations** — What was tried, what worked, what didn't.
3. **Implementation notes** — Specific configurations and setups.
4. **Operations lessons** — Things learned from running infrastructure.
5. **Lab stack** — What's running in the self-hosted lab.

## Content rules

- **Public only**: No private infrastructure details.
- **Stripped of secrets**: No IPs, hostnames, tokens, keys.
- **Educationally reusable**: Articles should teach a pattern, not
  document internal procedure.
- **Honest about trade-offs**: Describe what didn't work alongside what did.

## Design philosophy

Dark, minimal, type-focused. The UI should feel like reading a
well-formatted engineering notebook — practical, not decorative. See
[docs/design.md](design.md).

## Commands

```sh
npm run dev       # start dev server
npm run build     # production build
npm run preview   # preview build
```

## Branch strategy

- `main` — deployed to production via Cloudflare Pages.
- `feature/*` — feature branches, merged via PR.
- No `develop` or `staging` branches at this stage.
