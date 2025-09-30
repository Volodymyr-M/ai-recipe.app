# Guidance for AI Agents Working on Snap & Cook Marketing Site

## Mission
Maintain and evolve the Snap & Cook marketing website so it continues to convert curious visitors into confident app users by emphasizing real-world outcomes and delivering a trustworthy, accessible experience.

## Core Principles
- **Outcome-first storytelling:** Lead with how Snap & Cook improves the cook’s life before discussing features or technology.
- **Trust & credibility:** Retain data points, testimonials, and social proof. Any new claims must be plausible, consistent with `app_requirements.md`, and ideally sourced.
- **Non-intrusive design:** Preserve the dark, cinematic aesthetic and responsive layout while keeping text highly legible.

## Content Updates
- Keep heroic messaging aligned with the PRS vision (transforming photos into recipes tailored to the user).
- Mention key use cases (restaurant dish discovery, ingredient-based cooking, meal planning) when expanding copy.
- Store buttons must remain prominent above the fold and in the final CTA. Update `href` values only with official store URLs.
- Coordinate changes with legal documents only if instructed; do **not** edit `privacy_policy.html` or `terms_of_service.html` otherwise.

## SEO & Analytics
- Maintain the existing meta tags, canonical URL, and JSON-LD schema; update them deliberately when messaging shifts.
- Use descriptive section headings (`<h2>` or `<h3>`) and keep a single `<h1>` on each page.
- When adding media, prefer compressed or lazy-loadable assets and supply meaningful `alt` text.

## Styling & Front-End
- Extend `styles/landing.css` using the defined CSS custom properties. Avoid introducing new fonts without updating the Google Fonts import.
- Ensure new components scale on viewports down to 320px and respect existing spacing rhythm.
- Avoid breaking the layout for legal pages by keeping `styles/styles.css` untouched unless changes are specifically requested.

## Operational Notes
- Reference `README.md` for project structure and deployment habits.
- Document significant structural changes in the README so future contributors understand rationale.
- If build tooling or dependencies are introduced, add installation and usage notes to the README.

## Things to Avoid
- Removing or downgrading app store CTAs.
- Introducing autoplaying media or intrusive animations.
- Publishing unlicensed imagery—always verify rights before replacing placeholder assets.
- Pushing experimental features without providing a rollback strategy.
