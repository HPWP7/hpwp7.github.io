# TODO

Working list of improvements for the ITEna Solutions site, ordered by effort so quick wins get done first. Remember: **anything committed to `main` goes live immediately** on itenasolutions.com — treat merges as deploys.

## Quick wins (minutes, low risk)

- [x] Delete the unused `images/` folder — none of the three pages reference it (`index.html`, `Solutions.html`, `contactUs.html` only use `assets/Logo-transparent.png` and `assets/favicon.png`; everything else is inline SVG/CSS). ~14 leftover files from the pre-redesign site.
- [x] Resolve the `assets/favicon.png` vs `images/favicon.png` duplication — confirmed `assets/favicon.png` is the one referenced by all 3 pages; resolved by deleting `images/`.
- [x] Add `robots.txt` (allow all, point to sitemap).
- [x] Add a `sitemap.xml` listing the 3 pages.
- [x] Add Open Graph / Twitter Card meta tags (`og:title`, `og:description`, `og:image`, `twitter:card`) to all 3 pages.
- [x] Replace the `og:image`/`twitter:image` placeholder — built a proper 1200×630 banner (`assets/og-banner.png`, logo on the navy/red brand background with the new tagline) and wired it into all 3 pages.
- [x] Add a custom `404.html` at the repo root so broken links get a branded page instead of GitHub's default.

## Small (under an hour, touches a few files)

- [x] Footer copyright year — now computed via a small inline script (`#copyright-year` span) in all 4 pages instead of hardcoded. Also made the "25+ years" stat (`#years-experience`, index.html hero stat + Solutions.html SaaS copy) dynamic: `current year - 1999`, minus 1 before Sept 1 (company incorporated August 1999).
- [x] Analytics — restored the pre-redesign GA4 tag (`G-LVCDLNGH40`, gtag.js) that was dropped during the rewrite; added to `<head>` of all 4 pages (`index.html`, `Solutions.html`, `contactUs.html`, `404.html`).

## Medium (needs a decision, not just execution)

- [ ] Contact page has no real form, only `mailto:` links + embedded map. A working form needs a third-party backend since GitHub Pages has no server (e.g. Formspree, Web3Forms). Decide if `mailto:` is good enough or if a form is worth the extra dependency.
- [ ] "Insurance Agency SaaS" section: keep the "IN DEVELOPMENT" badge as-is (deliberately open-ended, no timeline implied), but the paragraph's "Currently under active development" line is inaccurate — the SaaS project hasn't actually started, this section exists to gauge market interest. **Target: January 2027** (deprioritized — Eurosure project has priority until then; some leads already exist independently of the site). When revisited, swap that line for an interest CTA, e.g. "Interested in early access? Get in touch." linking to `contactUs.html`.

## Large (structural investment)

- [ ] **Design system** (plan agreed 2026-07-14, not started — finalize details and implement later):
  - **Problem 1 — duplicated markup**: header/nav/footer blocks are copy-pasted byte-for-byte across `index.html`, `Solutions.html`, `contactUs.html`, `404.html` (only the active nav link differs). Any change means hand-editing 4 files and hoping nothing drifts.
  - **Problem 2 — duplicated styling**: colors/fonts/sizes are repeated as raw inline `style="..."` hex/px values on nearly every element, not just in the header — riskier than the markup duplication since a typo (e.g. `#4A5261` vs `#4A5162`) is invisible without a side-by-side diff.
  - **Agreed approach**: a small custom Node script, run at commit time (not a runtime/client-side include — no added JS dependency, still plain static output for GitHub Pages), that:
    1. Composes the header/nav/footer partials into each page's final HTML.
    2. Uses a shared stylesheet via `<link rel="stylesheet" href="styles.css">` (confirmed OK to drop the "fully self-contained per file" property now that a build step exists) — start by tokenizing colors (highest drift risk), then type scale, gradually replacing inline hex/px values; page-specific one-off layout (padding, grid) can stay inline.
  - Still to finalize before starting: exact script structure/partial format, how tokens are named, migration order across the 4 pages.
  - Worth doing once either (a) the site grows past today's 4 pages, or (b) hand-editing 4 files per header/footer/color change becomes painful — both already true, but deprioritized while the user is focused on the Eurosure project (see also the SaaS interest CTA item above, same reason).
