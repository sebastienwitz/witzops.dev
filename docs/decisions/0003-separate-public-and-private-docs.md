# ADR 0003: Separate public engineering content from private operations runbooks

| Field    | Value                                         |
|----------|-----------------------------------------------|
| Status   | Accepted                                      |
| Date     | 2026-05                                      |
| Deciders | Sebastien Witz                                |

## Context

WitzOps operates real infrastructure — virtualized hosts, network
equipment, storage, monitoring, and automation. This generates two
categories of documentation:

1. **Public engineering content**: Architecture patterns, tool
   evaluations, implementation guides, lessons learned. This content
   is valuable to share publicly and helps build an engineering
   portfolio.

2. **Private operations runbooks**: Step-by-step procedures against
   live systems, credential management, network topology, backup
   strategies, incident response procedures. This content is sensitive
   and must never be public.

A single repository cannot safely hold both categories. Even with
careful review, the risk of leaking operational details is too high.

## Options considered

### Separate repositories (chosen)

- **Public repository** (`witzops.dev`): Contains the Astro site source
  and all public-facing content.
- **Private repository**: Contains runbooks, configurations,
  credentials (encrypted), and operational procedures.

The public repository is built and deployed automatically. The private
repository is never exposed to CI/CD pipelines that could leak content.

### Single repository with content filtering at build time

- All content lives in one repo. A build-time filter selects what gets
  published.
- Rejected: Too easy to accidentally mark sensitive content as public.
  Build-time filtering adds complexity without a meaningful safety
  improvement over manual review.

### Single repository with everything public

- Rejected outright. Publishing operational runbooks, even sanitized,
  creates unnecessary risk.

## Decision

Maintain **separate repositories** for public engineering content and
private operations documentation.

## Consequences

### Positive

- Clear boundary: anything committed to the public repo is intentionally
  public. No filter, no ambiguity.
- Zero risk of build tools or CI pipelines accidentally exposing private
  content.
- Each repository can have its own access controls, CI configuration,
  and contribution workflows.
- Simplifies the mental model for contributors and agents: "this repo is
  public, act accordingly."

### Negative

- Content that straddles the boundary (e.g., an architecture note that
  references specific hardware) requires more effort to sanitize before
  publishing.
- Cross-referencing between public and private docs is limited to
  generic links or descriptions.
- Two repositories to maintain instead of one.
