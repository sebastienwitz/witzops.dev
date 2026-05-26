# witzops.dev

Public engineering notebook for WitzOps — infrastructure, automation,
observability, and AI-assisted engineering.

## Purpose

This repository contains the source for the public-facing site at
[witzops.dev](https://witzops.dev). The site serves as:

- A structured notebook for infrastructure and DevOps field notes.
- A publication layer that turns private operations work into reusable
  public engineering articles.
- A platform for documenting architecture decisions, tool evaluations,
  and implementation patterns.

## Stack

- **Framework**: [Astro](https://astro.build) 6 (static output)
- **Hosting**: Cloudflare Pages
- **CI**: GitHub Actions

## Local development

```sh
npm install
npm run dev       # starts dev server at http://localhost:4321
npm run build     # builds for production to ./dist/
npm run preview   # previews the production build locally
```

## Cloudflare Pages

The site is static Astro output and deploys to Cloudflare Pages.

| Setting              | Value           |
| -------------------- | --------------- |
| Framework preset     | Astro           |
| Build command        | `npm run build` |
| Output directory     | `dist`          |
| Production branch    | `main`          |

Every push to `main` triggers a production deploy. The site is fully static
with no server-side rendering and no runtime dependencies beyond the built
assets.

## Security and publication rules

This repository contains **public-facing content only**. Private
infrastructure details, IP addresses, internal hostnames, tokens,
keys, and runbook procedures belong in a separate private repository.

Before committing or publishing content:

- Strip private infrastructure details (IPs, hostnames, internal URLs).
- Remove secrets, tokens, and credentials.
- Avoid operational procedures that could be used to target running
  infrastructure.
- Keep content reusable and educational rather than operational.

See [docs/publication-rules.md](docs/publication-rules.md) for the full
policy.

## Documentation

- [AGENTS.md](AGENTS.md) — instructions for AI coding agents
- [CLAUDE.md](CLAUDE.md) — Claude-specific guidance
- [docs/agent-brief.md](docs/agent-brief.md) — project briefing for agents
- [docs/design.md](docs/design.md) — visual design direction
- [docs/architecture.md](docs/architecture.md) — technical architecture
- [docs/content-plan.md](docs/content-plan.md) — content structure and strategy
- [docs/roadmap.md](docs/roadmap.md) — project roadmap
- [docs/publication-rules.md](docs/publication-rules.md) — security and publication policy
- [docs/decisions/](docs/decisions/) — architecture decision records

## Repository hardening

Repository ruleset, branch protection, and code scanning recommendations are
documented in [docs/repository-hardening.md](docs/repository-hardening.md).

## License

MIT — see [LICENSE](LICENSE).
