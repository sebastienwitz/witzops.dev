# Homepage visual audit

Issue: #37

## Intent

This pass improves the homepage without rebuilding the whole visual system.

The goal is to move WitzOps away from a generic infrastructure notebook feeling and toward a more explicit positioning:

> Modernizing complex software systems with DevOps, AI, and pragmatic architecture.

The current design identity remains valid: dark, restrained, technical, public-safe. This PR adds more visual structure and clearer storytelling.

## References

Directional references only. The goal is not to clone them.

- Vercel: premium developer-product hero, crisp hierarchy, strong first viewport.
- Linear: polished dark UI, spacing discipline, subtle card treatments.
- Railway: infrastructure energy, visual systems, builder vibe.
- Cloudflare: trust, network/platform language, technical diagrams.

## Findings

### 1. First impression was too generic

The previous hero was clean but still sounded like a broad platform/ops site. It did not surface legacy modernization, DevOps industrialization, or AI-assisted engineering quickly enough.

Change made:

- sharpened the global tagline,
- rewrote the hero copy,
- added a visual engineering loop to clarify the operating model.

### 2. Homepage lacked visual anchors

The previous homepage was mostly text, tags, and simple cards. It was coherent but visually quiet.

Change made:

- added a hero-side visual panel,
- added a proof strip,
- added two storytelling panels,
- made project cards more visual.

### 3. Project cards needed stronger scanability

Project cards were clean but read like static notes.

Change made:

- added a small abstract visual area,
- added optional outcome text,
- made card metadata more explicit.

### 4. Visuals must stay public-safe

The site should not expose real private topology or customer details.

Direction kept:

- abstract diagrams,
- generic engineering loops,
- no real endpoint names,
- no private infrastructure map.

## Implemented in this pass

- Sharper site tagline in `src/data/site.ts`.
- Homepage hero refresh in `src/pages/index.astro`.
- AI-assisted engineering loop visual.
- Proof strip for source/control/amplifier positioning.
- Two storytelling panels:
  - modernization path,
  - design rule against fake dashboards.
- More visual `ProjectCard` component with optional `visualLabel` and `outcome` props.

## Still to do

This PR is only the first implementation slice.

Recommended next passes:

1. Add real project-specific links/actions on preview cards.
2. Create proper SVG assets for:
   - AI engineering loop,
   - legacy modernization map,
   - platform topology,
   - Replay Lab flow.
3. Add before/after screenshots to the issue or PR.
4. Review mobile rendering after deployment preview.
5. Consider a lightweight motion pass, but only if it remains restrained.

## Design constraints

- Keep Astro/Tailwind or plain component CSS as the source of truth.
- Avoid a full Figma rebuild.
- Avoid generic stock photography.
- Avoid AI clichés such as robot heads, glowing brains, and meaningless dashboards.
- Keep the site fast, readable, and public-safe.
