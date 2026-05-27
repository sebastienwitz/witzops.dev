# Homepage visual audit

Issue: #37

## Intent

This pass improves the homepage without rebuilding the whole visual system.

The goal is to move WitzOps away from a generic infrastructure notebook feeling and toward a more explicit positioning:

> Modernizing complex software systems with DevOps, AI, and pragmatic architecture.

The current design identity remains valid: dark, restrained, technical, public-safe. The homepage should feel sharper, not heavier.

## References

Directional references only. The goal is not to clone them.

- Vercel: premium developer-product hero, crisp hierarchy, strong first viewport.
- Linear: polished dark UI, spacing discipline, subtle card treatments.
- Railway: infrastructure energy and builder vibe.
- Cloudflare: trust, platform language, clear technical storytelling.

## Coherence check

The first design pass added too many explanatory blocks. The same message was repeated through the hero, visual loop, proof strip, focus tags, story panels, and card outcomes.

That made the homepage richer, but also more crowded and less confident.

The adjusted direction is deliberately simpler:

1. Say the positioning once in the hero.
2. Use focus tags as quick scanning aids.
3. Put the concrete work tracks immediately after.
4. Keep only one short operating-principle block.

## Implemented in the simplified pass

- Sharper site tagline in `src/data/site.ts`.
- Simpler homepage hero with a subtle abstract background accent.
- Focus tags reduced and deduplicated.
- Project cards kept visual, but without heavy pseudo-diagram panels.
- Card outcomes shortened to one practical value statement.
- Removed the separate proof strip.
- Removed the large hero-side engineering loop panel.
- Removed the second story panel.
- Kept one short manifesto block: from legacy complexity to controlled delivery.

## Remaining direction

Next improvements should add specificity, not more generic decoration.

Recommended next passes:

1. Add real project-specific links/actions on preview cards.
2. Replace abstract card labels with project-specific SVG icons only if they add clarity.
3. Add one strong hero asset later, but keep it ambient rather than explanatory.
4. Add before/after screenshots to the issue or PR.
5. Review mobile rendering after deployment preview.

## Design constraints

- Keep Astro/Tailwind or plain component CSS as the source of truth.
- Avoid a full Figma rebuild.
- Avoid generic stock photography.
- Avoid AI clichés such as robot heads, glowing brains, and meaningless dashboards.
- Do not repeat the same positioning message across multiple blocks.
- Keep the site fast, readable, and public-safe.
