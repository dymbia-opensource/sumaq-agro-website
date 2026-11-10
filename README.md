# SumaqAgro — Landing Page

[![Release](https://img.shields.io/badge/release-v3.2.0-brightgreen.svg)](#versioning-and-workflow)
[![Stack](https://img.shields.io/badge/stack-HTML5%20%7C%20CSS3%20%7C%20JavaScript%20vanilla-blue.svg)](#technology-stack)
[![i18n](https://img.shields.io/badge/i18n-ES%20%7C%20EN-orange.svg)](#technical-features)
[![Course](https://img.shields.io/badge/UPC-1ASI0729%20Open%20Source-red.svg)](https://www.upc.edu.pe/)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](LICENSE.md)

Official repository for the **SumaqAgro Landing Page**, the precision agriculture SaaS platform developed by the Peruvian startup **Dymbia**. A static, responsive, bilingual (Spanish/English) website built with HTML5, CSS3, and vanilla JavaScript, without frameworks or runtime dependencies, for fast loading on rural mobile networks.

Project developed for the course *1ASI0729 Open Source Applications Development* (UPC, Academic Term 2026-20), following GitFlow and Conventional Commits.

---

## Academic Information

- **Institution:** Universidad Peruana de Ciencias Aplicadas (UPC)
- **Faculty:** Faculty of Engineering
- **Degree Program:** Software Engineering
- **Course:** 1ASI0729 - Open Source Applications Development
- **Academic Term:** 2026-20
- **Instructor:** Velasquez Nuñez, Angel Augusto

---

## Project Description

**Startup:** Dymbia  
**Product:** SumaqAgro

**Dymbia** aims to close the digitalization gap in Peru's agrifood sector, focusing on small and medium-sized growers, agricultural cooperatives, and technical advisors in the **Andean potato** and **specialty coffee** value chains.

This landing page is SumaqAgro's **commercial entry point**: it communicates the value proposition through the slogan *"Cultivate with Information. Decide with Precision"*, introduces the team and subscription plans, and guides visitors toward plan inquiries.

### Solutions Presented on the Landing Page

1. **Satellite Vigor and Moisture Monitoring:** NDVI and NDWI through Sentinel-2, without field sensors.
2. **Cost Accounting per Plot:** financial records and minimum selling price.
3. **Digital Harvest Quality Certification:** PDF certificates with an auditable QR seal.
4. **Agronomic Prescriptions and Alerts:** notifications about frost, pests, and water stress.

---

## Website Sections

The landing page follows a conversion journey: **value proposition → problem → solution → proof → pricing → trust → action**. Each block addresses a user story from EPIC-01 in the project report.

| # | Section | Anchor | Purpose | US |
|---|---|---|---|---|
| 1 | Hero | `#hero` | Value proposition, animated Andean landscape, and "View plans" CTA | US-01 |
| 1b | Platform showcase | `#platform` | Real application screenshot, scrolling marquee, and platform highlights | US-01 |
| 2 | The challenge | `#problem` | Grower challenges and official statistics with sources (MIDAGRI, INEI, JNC) | US-01 |
| 3 | Solutions | `#solutions` | Four modules with profile filters (Farmer, Cooperative, Advisor) | US-06 |
| 4 | How it works | `#how-it-works` | Three usage steps and the Crop Health view | US-06 |
| 5 | Demo | `#demo` | Lazy-loaded video (thumbnail → player) | US-05 |
| 6 | Who do we help? | `#audience` | Animated profile gallery, benefits, recommended plan, and CTA per segment | US-06 |
| 7 | Plans | `#plans` | Seed, Cooperative Pro, and Technical Advisor with monthly/annual billing | US-07 |
| 8 | Impact and testimonials | `#impact` | Impact goals (Lean UX hypotheses) and testimonial carousel | US-08 |
| 9 | About us and team | `#about`, `#team` | Mission, vision, profiles with GitHub links, and team video placeholder | US-04 |
| 10 | Frequently asked questions | `#faq` | Answers to questions before signing up | — |
| 11 | Final CTA | `#cta` | Profile selector that recommends a plan and prepares an email inquiry | US-07 |
| 12 | Footer | — | Navigation, contact information, and legal policies in a modal dialog | US-09 |

### Legal Pages

- [Privacy Policy](public/policy.html)
- [Terms of Service](public/service.html)
- [Cookie Policy](public/cookie.html)

---

## Technical Features

- **Bilingual ES/EN:** dynamic translation through `data-i18n` (content) and `data-i18n-attr` (attributes such as `alt` or `aria-label`); the initial language comes from `localStorage` or the browser.
- **Billing selector:** switches monthly/annual prices, displays the monthly equivalent, and synchronizes the billing period (`/month` · `/year`) with the active language.
- **Conversion:** the primary CTA is repeated in the hero, segments, plans, and closing section; plan buttons and the final profile selector prepare an email with the selected plan and billing period.
- **Legal policies in a modal:** legal links open a `<dialog>` containing the legal page content and fall back to the full page when necessary.
- **Responsive design:** media queries and a mobile hamburger menu for mobile, tablet, and desktop layouts.
- **SEO and Open Graph:** meta tags, a descriptive title, and `og:*` properties in the `<head>`.
- **Accessibility:** semantic HTML, `aria-labelledby`, `aria-live`, dynamic language control labels, and reduced-motion support.
- **Performance:** optimized WebP images, lazy-loaded images and video, and self-hosted Inter fonts.
- **Shared layout:** header and footer partials loaded from `public/assets/partials/`.
- **External SVG assets:** hero layers, community illustrations, and the reusable GitHub icon stored in `public/assets/images/svg/`, preserving parallax, animations, and gallery playback controls.

---

## Technology Stack

| Layer | Technology |
|---|---|
| Markup | Semantic HTML5 |
| Styles | CSS3 (`public/assets/styles`) |
| Logic | Vanilla JavaScript (`public/assets/scripts`) |
| i18n | Translation modules (`public/assets/scripts`) |
| Typography | Poppins (headings, Google Fonts) and Inter (body text, self-hosted) |
| Iconography | Material Symbols Outlined and SVG (`public/assets/images/svg/`) |
| Project management | Jira, Miro, GitHub |

> **Scope Note:** SumaqAgro is exclusively cloud software; it does not include physical sensors or IoT devices.

---

## Local Setup

No build step or dependency installation is required.

```bash
# 1. Clone the repository
git clone https://github.com/dymbia-opensource/sumaqAgro-landing-page.git
cd sumaqAgro-landing-page

# 2. Serve the public directory locally (requires Python):
python3 -m http.server 8080 --directory public
# → http://localhost:8080
```

On Windows, you can use `py -m http.server 8080 --directory public`. Use a local HTTP server so the shared partials, legal dialogs, and SVG animation controls work correctly.

## Directory Structure

```text
sumaqAgro-landing-page/
├── public/
│   ├── assets/
│   │   ├── fonts/                  # Inter (400–700) in .ttf format
│   │   ├── images/                 # PNG logos, WebP photos, and application screenshots
│   │   │   └── svg/                # External vector illustrations and icons
│   │   │       ├── community-advisor.svg
│   │   │       ├── community-cooperative.svg
│   │   │       ├── community-farmer.svg
│   │   │       ├── github.svg
│   │   │       ├── hero-andes.svg
│   │   │       ├── hero-foreground.svg
│   │   │       ├── hero-mountains.svg
│   │   │       ├── hero-sky.svg
│   │   │       └── hero-terraces.svg
│   │   ├── js/
│   │   │   ├── i18n/               # Internationalization dictionaries
│   │   │   │   ├── en.js           # English translations
│   │   │   │   └── es.js           # Spanish translations
│   │   │   └── script.js           # Main logic, mobile menu, billing, and language switching
│   │   ├── partials/               # Shared layout components
│   │   │   ├── _header.html        # Header and navigation
│   │   │   └── _footer.html        # Footer
│   │   └── styles/
│   │       └── styles.css          # Global styles and responsive media queries
│   ├── pages/                      # Secondary and legal pages
│   │   ├── cookie.html             # Cookie Policy
│   │   ├── policy.html             # Privacy Policy
│   │   └── service.html            # Terms of Service
│   ├── index.html                  # Main page
│   └── 404.html                    # Not-found page (Cloudflare Pages)
├── package.json
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.MD
├── LICENSE.md
└── README.md
```

## Development Team

| Member |
|---|
| Solorzano Sullca, Benjamin |
| Tejada Pumacayo, Yamil Jared |
| Vargas Enriquez, Jose Carlos |
| Sanca Condori, Miguel |
| Duarte Ruffner, Drago Derick |

---

## Versioning and Workflow

- **GitFlow:** `main` (production), `develop` (integration), `feature/*`, `release/*`, and `fix/*` branches.
- **Conventional Commits:** `feat(landing): …`, `fix(i18n): …`, `style(footer): …`.
- **Releases:**
    - `v1.0.0` — Initial landing page, i18n, SEO, and team.
    - `v1.1.0` — Responsive layout, mobile menu, and legal page fixes.
    - `v3.0.0` — Conversion-oriented redesign (problem, how it works, FAQ, plan selector) and image optimization.
    - `v3.1.0` — Demo video, testimonial carousel, and impact goals.
    - `v3.2.0` — Upgrades and bug fixes.

---

## License

Distributed under the **CC BY-NC-SA 4.0** license. See [`LICENSE.md`](LICENSE.md).

© 2026 Dymbia — SumaqAgro.
