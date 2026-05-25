# ADR 0001: Use Astro as the static site generator

| Field    | Value                                         |
|----------|-----------------------------------------------|
| Status   | Accepted                                      |
| Date     | 2026-05                                      |
| Deciders | Sebastien Witz                                |

## Context

witzops.dev needs a static site that:

- Serves as an engineering notebook with articles, architecture
  records, and project pages.
- Builds to static HTML — no runtime server or database.
- Supports Markdown content with component-based pages where needed.
- Ships minimal or zero JavaScript to the client.
- Is straightforward to set up, build, and deploy.

## Options considered

### Astro

- Static-first, output is HTML with zero JS by default.
- Island architecture allows selective hydration if ever needed.
- First-class Markdown and content collection support.
- Component model uses `.astro` files — familiar syntax, no new
  framework to learn.
- Mature ecosystem with good documentation.

### Next.js (static export)

- Overkill for a content site. Brings React runtime weight and a
  complex configuration surface for a static export.
- Static export is a secondary feature, not the primary design goal.

### Hugo

- Fast builds, pure static output.
- Go templating is less ergonomic for component-heavy pages.
- Content model works well for blogs but less so for mixed
  content/component pages.

### Eleventy

- Flexible and lightweight.
- Requires more configuration and plugin setup to reach feature
  parity with Astro's built-in capabilities.

## Decision

Use **Astro** with static output mode.

## Consequences

### Positive

- Zero JavaScript shipped to the client by default. Fast page loads.
- Content collections provide type-safe Markdown handling.
- `.astro` components keep logic and template co-located without
  heavyweight framework abstractions.
- Simple build pipeline: `npm run build` produces `./dist/`.

### Negative

- Astro 6 is relatively new. Breaking changes between major versions
  are possible and have occurred in the past.
- Smaller plugin ecosystem compared to Next.js.
- Limited support for complex client-side interactivity (not a concern
  for this project).
