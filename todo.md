# TODO

Working list of improvements for the ITEna Solutions site, ordered by effort so quick wins get done first. Remember: **anything committed to `main` goes live immediately** on itenasolutions.com — treat merges as deploys.

## Quick wins (minutes, low risk)

- [x] Delete the unused `images/` folder — none of the three pages reference it (`index.html`, `Solutions.html`, `contactUs.html` only use `assets/Logo-transparent.png` and `assets/favicon.png`; everything else is inline SVG/CSS). ~14 leftover files from the pre-redesign site.
- [x] Resolve the `assets/favicon.png` vs `images/favicon.png` duplication — confirmed `assets/favicon.png` is the one referenced by all 3 pages; resolved by deleting `images/`.
- [x] Add `robots.txt` (allow all, point to sitemap).
- [x] Add a `sitemap.xml` listing the 3 pages.
- [ ] Add Open Graph / Twitter Card meta tags (`og:title`, `og:description`, `og:image`, `twitter:card`) to all 3 pages — needs one shareable image (e.g. logo on navy background) to point `og:image` at.
- [ ] Add a custom `404.html` at the repo root so broken links get a branded page instead of GitHub's default.

## Small (under an hour, touches a few files)

- [ ] Footer copyright year (`© 2026`) is hardcoded in `Solutions.html` and `contactUs.html` — either bump manually each January, or replace with a tiny inline `<script>document.write(new Date().getFullYear())</script>` so it never goes stale (small tradeoff: the one bit of JS on an otherwise JS-free site).
- [ ] Decide on analytics (e.g. a privacy-friendly option like Plausible/Fathom, or GA4) and add the snippet to all 3 pages if wanted.

## Medium (needs a decision, not just execution)

- [ ] Contact page has no real form, only `mailto:` links + embedded map. A working form needs a third-party backend since GitHub Pages has no server (e.g. Formspree, Web3Forms). Decide if `mailto:` is good enough or if a form is worth the extra dependency.
- [ ] "Insurance Agency SaaS" section is marked "IN DEVELOPMENT" — revisit copy/status as that project progresses (content task, not code).

## Large (structural investment)

- [ ] **Design system**: extract the repeated header/nav/footer/CTA-button/stat-card markup (currently duplicated verbatim across all 3 HTML files — see `CLAUDE.md`) into a small component library authored/iterated on in Claude Design, synced locally via `/design-sync` and `DesignSync`. Worth doing once either (a) the site grows past 3 pages, or (b) visual design iteration becomes frequent enough that hand-editing 3 files per change gets painful. Start with one low-risk component (e.g. the CTA button or stat card) to validate the workflow before migrating the header/footer.
