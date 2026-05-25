# Content plan

What content each section of the site carries and how it is organized.

## Site structure

```
/               Home — overview, focus areas, preview content
/projects       Project listings — structured summaries of ongoing work
/architecture   Architecture patterns and system design notes
/lab-stack      Lab infrastructure — what's running and why
/blog           Articles — tool evaluations, lessons, implementation notes
/about          Who this is, what WitzOps does, contact
```

## Page details

### Home (`/`)

- Short description of what the site is.
- List of focus areas (tags): self-hosted infra, DevOps automation,
  AI engineering workflows, observability, IaC, secure remote access,
  legacy modernization.
- Preview cards linking into the rest of the site.

### Projects (`/projects`)

- Catalog of projects with status indicators (e.g. "In setup",
  "Active", "Framing", "Complete").
- Each project: title, summary, status, relevant tags.
- Links to detailed pages or relevant blog posts.

### Architecture (`/architecture`)

- Architecture decision records (ADRs).
- System design patterns used in the lab.
- Diagrams and explanatory notes.

### Lab Stack (`/lab-stack`)

- Inventory of what runs in the self-hosted lab.
- Tooling choices and rationale.
- Configuration patterns (sanitized).

### Blog (`/blog`)

- Long-form articles.
- Categories: tool evaluations, implementation guides, post-mortems,
  operations lessons.
- Chronological, no pagination at small scale.

### About (`/about`)

- Who maintains WitzOps.
- Purpose and scope.
- Contact information.

## Content pipeline

1. Work happens in the private lab and runbooks repository.
2. Lessons, patterns, and architecture decisions are identified as
   candidates for publication.
3. Content is written, sanitized per [publication-rules.md](publication-rules.md),
   and committed to this repository.
4. Published via merge to `main`, deployed automatically through
   Cloudflare Pages.

## Content format

- Markdown where possible (blog posts, ADRs), rendered through Astro's
  content collections.
- Astro components for structured content (project cards, tag lists,
  callouts).
- Diagrams via Mermaid or static SVG, committed to the repo.

## What stays private

Operational runbooks, monitoring configurations, backup strategies,
network segmentation details, credential management procedures. These
are sensitive and belong in the private repository. The public site
should be buildable without any private content dependencies.
