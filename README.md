# Snap & Cook Marketing Website

A single-page marketing site that introduces the Snap & Cook mobile app and focuses on the outcomes it delivers—helping people turn food photos into recipes they can cook tonight.

## Page Goals
- Communicate the core value proposition: going from inspiration to a personalized, guided cooking plan in minutes.
- Highlight the real-life outcomes users care about (recreating dishes, reducing waste, achieving dietary goals, staying inspired).
- Drive installs on iOS and Android via prominent app store calls-to-action.
- Reinforce trust with social proof, metrics, and clear answers to common questions.
- Provide a search-friendly, performant experience with structured data and optimized metadata.

## Project Structure
- `index.html` – Main landing page with semantic sections (`hero`, `outcomes`, `how-it-works`, `proof`, `faq`, `final-cta`).
- `styles/landing.css` – Custom marketing styles, responsive layout rules, and design tokens.
- `styles/styles.css` – Legacy stylesheet used by legal pages. Leave untouched unless updating those pages.
- `privacy_policy.html` / `terms_of_service.html` – Existing legal pages that remain unchanged.

## Key Content Elements
- Outcome-first copy: framing benefits through user success instead of feature lists.
- Metrics and testimonials for credibility; placeholder press logos illustrate future PR placement.
- FAQ answers the high-intent questions captured in the PRS (lighting, dietary needs, planning, device support).
- Dual CTAs for Google Play and App Store (placeholder URLs for now) repeated in hero and final sections.

## SEO & Analytics Considerations
- Optimized `<title>` and meta description crafted around “food photo to recipe” searches.
- Open Graph and Twitter cards configured for richer link previews.
- Canonical URL (`https://ai-recipe.app/`) set to avoid duplicate content issues.
- JSON-LD `MobileApplication` schema included for app store discovery.
- Semantic headings (single `<h1>`, descriptive `<h2>`s) to improve crawl comprehension.

## Working With the Site
1. **Local preview:** open `index.html` in a browser or serve with a lightweight HTTP server (e.g., `python3 -m http.server`).
2. **Styles:** extend `styles/landing.css` using the existing design tokens defined under `:root`.
3. **Imagery:** current photos use public Unsplash URLs; replace with licensed assets before launch.
4. **Store links:** update `href` attributes on the CTA buttons when production store URLs are ready.
5. **Accessibility:** maintain descriptive alt text for meaningful images and ensure new color additions meet WCAG contrast.
6. **Performance:** host SVG badges locally in production to reduce third-party requests, and optimize hero imagery if self-hosting.

## Deployment Notes
- The repo is structured for static hosting (e.g., GitHub Pages). Ensure `CNAME` remains intact for the `ai-recipe.app` domain.
- If adding build tooling, document commands here and keep the default static output in `/` for existing hosting setups.
