# ADR 0002: Deploy to Cloudflare Pages

| Field    | Value                                         |
|----------|-----------------------------------------------|
| Status   | Accepted                                      |
| Date     | 2026-05                                      |
| Deciders | Sebastien Witz                                |

## Context

witzops.dev needs a hosting platform for a static Astro site. The
requirements are:

- Serve static HTML, CSS, and assets from a global CDN.
- Automatic deployments from the `main` branch.
- Custom domain support.
- Free or low cost at the project's scale.
- HTTPS by default.

## Options considered

### Cloudflare Pages

- Native git integration — push to `main`, site deploys automatically.
- Global CDN with good performance.
- Free tier is generous and sufficient for a static site at this scale.
- HTTPS enforced by default.
- Already using Cloudflare for DNS — consolidating on one platform
  reduces operational overhead.

### GitHub Pages

- Free and integrated with GitHub.
- Custom domain support with HTTPS.
- No build pipeline for Astro by default — requires a GitHub Actions
  workflow to build and deploy, adding operational complexity compared
  to Cloudflare's native build integration.

### Vercel

- Excellent developer experience and build integration.
- Free tier adequate for this project.
- Adds a vendor dependency outside the existing Cloudflare ecosystem.

### Netlify

- Similar feature set to Vercel.
- No compelling advantage over Cloudflare Pages given existing
  Cloudflare usage.

## Decision

Use **Cloudflare Pages** for hosting and deployment.

## Consequences

### Positive

- Automatic deployments from `main` branch with no additional
  configuration beyond connecting the repository.
- Global CDN, HTTPS, custom domain — all included.
- Consolidates on Cloudflare (already used for DNS), reducing the
  number of platforms to manage.
- Build logs and preview deployments available.

### Negative

- Vendor lock-in to Cloudflare. Migrating to another platform would
  require reconfiguring DNS and deployment pipelines.
- Cloudflare's build environment uses a specific Node.js version
  matrix; version mismatches between local and build environment are
  possible and need to be monitored.
