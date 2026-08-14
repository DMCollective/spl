# Speed Projects Lab — Website Consolidation & Redesign
## Design Brief

**Client:** Speed Projects Lab (SPL), Richmond BC
**Prepared by:** Digital Marketing Collective
**Date:** August 13, 2026
**Status:** Draft v2 — for review (positioning and visual direction revised)

---

## 1. Executive summary

Speed Projects Lab currently operates **four separate websites** across three domains, totalling **528 indexed URLs**. Each runs its own WordPress install, its own navigation, its own copy of the About/Contact/Reviews/Financing pages, and its own booking path. The primary domain — the strongest asset in the portfolio — is being spent on a splash page that asks visitors to choose a door before they've been sold anything.

This project consolidates all four properties into a single site at `speedprojectslab.com`, rebuilt on a modern static architecture, with one navigation, one funnel, one content model, and one design system.

The strategic case is simple: SPL is not four businesses. It is one shop that protects, tunes, maintains, and shoes the same car for the same customer. The website should behave the way the business does.

**Headline numbers**

| Metric | Current | Target |
|---|---|---|
| Domains / subdomains | 4 | 1 |
| WordPress installs | 4 | 0 |
| Duplicate "About Us" pages | 3 | 1 |
| Duplicate "Contact Us" pages | 3 | 1 |
| Total indexed URLs | 528 | ~185 (after demo-content cull) |
| Portfolio projects | 367 (buried) | 367 (surfaced as proof) |
| Published blog posts | 0 (3 blog landing pages) | Editorial calendar |

---

## 2. Current state audit

### 2.1 The four properties

| Property | URLs | Role today | Assessment |
|---|---|---|---|
| `speedprojectslab.com` | 406 | Splash / chooser page | Highest authority, lowest utility. Holds all 367 portfolio items. |
| `paintprotection.speedprojectslab.com` | 41 | PPF, coatings, tint, detailing | The most developed property. Strong local SEO landing pages. |
| `performance.speedprojectslab.com` | 23 | ECU tuning, coding, maintenance | Thinnest content. Highest-margin services. |
| `vancitytires.com` | 58 | Tire & wheel retail | Effectively unlaunched — see 2.5. |

### 2.2 Platform

All four run **WordPress with Yoast SEO**, on what appears to be a multipurpose commercial theme (the `project-details`, `product-details`, `team`, and `portfolio` custom post types are theme-provided, not custom). WooCommerce is installed on `speedprojectslab.com`, `performance.`, and `vancitytires.com` — three separate carts, three separate `/my-account/`, `/cart/`, `/checkout/` flows.

Four installs means four plugin update cycles, four security surfaces, four theme licences, and four places a change to the phone number has to be made.

### 2.3 Duplicate content — the core SEO problem

The following slugs exist on **two or more** domains, serving substantially similar content:

`/about-us/` · `/contact-us/` · `/reviews/` · `/financing/` · `/book-now/` · `/tuning-coding/` · `/terms-conditions/` · `/site-map/` · `/thank-you/` · `/careers/` · `/brands/` · `/shop/` · `/cart/` · `/checkout/` · `/my-account/` · `/ceramicpro/` · `/sliplo/` · `/portfolio/` · `/revivifycoatings/` · `/window-nano-coating/` · `/xpel-ultimate-plus-black-ppf/` · `/xpel-fusion-plus-ceramic-coating/` · `/xpel-automotive-window-tint/` · `/xpel-vision-window-film/` · `/stek-dynoflex-windshield-protection-film/` · `/rivian-xpel-paint-protection-film/`

Twenty-six duplicated paths. Google has to pick a winner for each, and the three properties compete with each other for the same Vancouver PPF and tuning queries. Consolidation resolves this by definition.

### 2.4 NAP inconsistency

The suite number differs between properties:

- `speedprojectslab.com` and `paintprotection.` — **401**-5940 No. 6 Road
- `performance.` — **403**-5940 No. 6 Road

Local search ranking depends on Name/Address/Phone consistency across the web. If both units are genuinely occupied, one must still be designated the canonical business address and used everywhere, with the second mentioned only as "additional bays." **This needs confirming before build.**

Phone and email are consistent: **+1 604-337-8728** / **info@speedprojectslab.com**

### 2.5 Vancity Tires is unlaunched

Of 58 URLs on `vancitytires.com`, **48 are unmodified theme demo content**: WooCommerce products called *Elegant Sunglasses*, *Wool Beanie Hat*, and *Brown Winter Boots*; staff pages for *Jane Doe*, *John Doe*, and *Harry Hoe*; lorem ipsum blog posts dated 2015; and a `hello-world` post from April 2026.

Only 10 pages are real: home, `/tires/`, `/promos/`, `/contact-us/`, `/financing/`, `/about-us/`, `/tire-buying-guide/`, `/tire-protection-plan/`, `/terms/`, `/privacy-policy/`.

**Implication:** there is almost no SEO equity to preserve here, which makes folding tires into the main site a low-risk, high-upside move. The 48 demo URLs should return 410 Gone, not redirect.

### 2.6 The portfolio is the buried asset

367 project pages documenting real work: *Lamborghini Aventador SV ECU tuning*, *Bugatti SlipLo install*, *Bentley Bentayga XPEL Ultimate Plus*, *Ferrari 458 Italia ceramic coating*. Years of documented craftsmanship, sitting behind a splash page, disconnected from the service pages it should be selling.

This is the single biggest content opportunity in the project. Rebuilt as a filterable gallery — by make, by service, by model — and cross-linked into every service page, it becomes the proof engine for the entire site.

### 2.7 Other findings

- **Three blog landing pages, zero blog posts.** `/blog/`, and `/blog-2-0/` on both subdomains. No post sitemap exists on any SPL domain.
- **Trust signals are real and underused.** 267 Google reviews at 5.0, XPEL certified installer, lifetime workmanship warranty. These appear inconsistently and below the fold.
- **Established 2017** — eight years of operating history, barely mentioned.
- **Slug/content mismatch on a portfolio entry.** `/project-details/bugatti-chiron-sliplo-install/` has an H1 and meta title of *"Bugatti Veyron SlipLo Install."* One of the two is wrong. Worth checking during migration — there are likely others across 367 entries.
- **A service slug occupied by a case study.** `/ppf-redo-correction-vancouver/` carries a service-intent URL and meta title but its H1 is *"Porsche Cayman 718 – Full PPF Redo & Restoration."* The page is ranking on a service term while presenting as a single project. In the new IA, `/paint-protection/ppf/correction/` becomes a proper service page and the Cayman becomes a portfolio entry linked from it.
- **Leftover migration asset.** At least one live image is still served from `5bo.2ac.mywebsitetransfer.com` — a staging host from a previous site move. A dependency on infrastructure nobody is maintaining.
- **The PPF geo pages are genuinely good.** Spot-checked seven of them; all live, all with distinct, well-written, locally-specific content and correct meta titles. These are the pages the redirect map must protect above all others.

---

## 3. Strategic objectives

**Primary**

1. **Consolidate authority.** One domain accumulating all link equity, all reviews, all content — instead of four splitting it.
2. **Convert the splash page into a selling homepage.** The strongest URL in the portfolio should carry the strongest pitch, not a menu.
3. **Cross-sell across service lines.** A customer who books PPF on a new Porsche is a candidate for ceramic, tint, tuning, and tires over the following three years. Four separate sites make that journey impossible; one site makes it the default.

**Secondary**

4. Preserve the local SEO gains already earned by the PPF geo pages (`ppf-cost-vancouver`, `tesla-ppf-vancouver`, `full-vehicle-ppf-vancouver`, etc.).
5. Reduce maintenance cost from four WordPress installs to one static build.
6. Give the portfolio a job.

### Success metrics

| Metric | Baseline | 6-month target |
|---|---|---|
| Quote form submissions / month | *TBD — need analytics* | +40% |
| Organic sessions (all properties combined) | *TBD* | +25% |
| Non-brand organic keywords in top 10 | *TBD* | +50% |
| Pages per session | *TBD* | +30% (cross-sell indicator) |
| Largest Contentful Paint | *TBD — measure current* | < 2.0s |
| Multi-service customers | *TBD* | Establish tracking |

*Analytics access is required to set real baselines — see Open Questions.*

---

## 4. Audience

### Primary — The New Car Owner
Just took delivery of a Tesla, Porsche, BMW, Audi, Rivian, or Range Rover. Wants it protected before the first rock chip. Researching PPF for the first time, comparing three shops, doesn't know what "Ultimate Plus" means yet. **High intent, short window, price-anxious but quality-motivated.**

*Needs:* clear package tiers, real cost ranges, before/after proof on their exact model, easy quote request, reassurance about warranty and installer certification.

### Secondary — The Enthusiast
Owns a BMW M-car, Golf R, WRX, or Mustang. Wants more power, better handling, DME unlock, custom coding. Deeply researched, reads forums, knows the tuner names (ETG, Pro Tuning Freaks, DTE). **Skeptical of marketing, convinced by specifics.**

*Needs:* technical depth, dyno numbers, supported platforms by model and engine code, evidence the shop has done their exact car.

### Tertiary — The Retained Customer
Already a client. Comes back for maintenance, tires, seasonal swaps, warranty work. **Convenience-driven, relationship-based.**

*Needs:* fast booking, service history, no re-explaining who they are.

**The insight connecting all three:** these are frequently the *same person* at different points in the ownership cycle. The current site architecture actively prevents SPL from monetizing that.

---

## 5. Positioning

> **Speed Projects Lab is Metro Vancouver's paint protection studio for people who actually care about their cars — and the same shop keeps them running once they're protected.**

**Protection leads.** PPF, ceramic coating, and finish work are the front door: they're what the business specialises in, what the strongest content ranks for, and what brings a new customer through the door within days of taking delivery. Performance, maintenance, and tires are real revenue and stay fully built out — but they sit behind protection in the hierarchy, framed as *"also under this roof"* rather than as equal doors. That's a change from the earlier draft of this brief, which weighted all four divisions equally and diluted the specialism.

The name already contains the rest of the idea. "Laboratory" implies method, measurement, and precision — not a garage with a lift and a hunch. The current sites use the word and then never cash the cheque.

**Tone: cinematic luxury.** The audience is enthusiasts protecting cars they chose deliberately. They don't need convincing the car is worth protecting; they need evidence the shop is worth trusting. That calls for restraint — specific detail, real numbers, and photography given room — not enthusiasm.

**Voice:** specific, calm, slightly understated. Numbers over adjectives. *"Wrapped past the edges so there's no visible line"* beats *"premium quality installation."* Never "unmatched," "unrivaled," "top-tier," or "one-stop shop."

**What we are not:** a discount chain, a dealership add-ons desk, a body shop, or a tuning garage that also does film.

---

## 6. Information architecture

### 6.1 Principles

1. **Service-first, not brand-first.** Customers search "Tesla PPF Vancouver," not "XPEL Ultimate Plus." Product brands live *inside* service pages as credibility, not as top-level nav.
2. **Three clicks to a quote from anywhere.**
3. **Every service page pulls its own portfolio proof** automatically, filtered by service tag.
4. **One canonical page per service.** No duplicates, ever.

### 6.2 Proposed sitemap

```
/                                       Home
│
├── /paint-protection/                  Hub
│   ├── /ppf/                           Paint protection film (canonical)
│   │   ├── /full-vehicle/
│   │   ├── /partial-front-end/
│   │   ├── /stealth-matte/
│   │   ├── /cost/                      ← preserves ppf-cost-vancouver
│   │   ├── /correction/                ← preserves ppf-redo-correction
│   │   ├── /tesla/                     ← hub for Tesla PPF
│   │   │   ├── /model-3/
│   │   │   └── /model-y/
│   │   └── /rivian/
│   ├── /ceramic-coating/
│   │   ├── /xpel-fusion-plus/
│   │   ├── /ceramic-pro/
│   │   └── /revivify/
│   ├── /windshield-protection/
│   │   ├── /exoshield/
│   │   └── /stek-dynoflex/
│   ├── /window-tint/
│   │   ├── /xpel-prime-xr/
│   │   └── /xpel-vision/
│   ├── /vehicle-wraps/
│   ├── /detailing/
│   └── /sliplo/                        Under-bumper protection
│
├── /performance/                       Hub
│   ├── /ecu-tuning/
│   │   ├── /etg/
│   │   ├── /pro-tuning-freaks/
│   │   └── /dte-chip-tuning/
│   ├── /bmw-coding/
│   ├── /dme-unlock/                    ← preserves bmw-dme-unlock-service-richmond
│   ├── /track-prep/
│   ├── /accessories-retrofits/
│   └── /maintenance/
│
├── /tires/                             Hub (absorbs Vancity Tires)
│   ├── /shop/
│   ├── /buying-guide/
│   ├── /protection-plan/
│   └── /promos/
│
├── /work/                              Portfolio — 367 projects, filterable
│   └── /work/[slug]/
│
├── /brands/                            XPEL, Ceramic Pro, Revivify, ETG, DTE…
├── /reviews/
├── /about/
├── /blog/
├── /financing/
├── /careers/
├── /contact/
├── /book/                              Booking / quote request
└── /shop/                              E-commerce (see Open Questions)
```

**Result: ~65 canonical pages** (down from 113 across four sites) plus 367 portfolio entries.

### 6.3 Primary navigation

```
[SPL logo]   Paint Protection ▾   Performance ▾   Tires ▾   Work   About ▾      604-337-8728   [Get a Quote]
```

Mega-menu on the three service dropdowns, each showing the service list plus a featured recent project from that category. Phone number always visible — it is the highest-converting element on a local service site and currently it is missing from the main domain entirely.

Sticky mobile bar: **Call** · **Quote** · **Book**.

### 6.4 Homepage structure

1. **Hero** — full-bleed vehicle work, one headline, primary CTA (Get a Quote), secondary (See our work). Phone visible.
2. **Trust bar** — 5.0 ★ / 267 reviews · XPEL Certified · Est. 2017 · Lifetime workmanship warranty
3. **Three doors, sold not listed** — Protect / Perform / Roll. Each with a real outcome line, not a category label.
4. **Featured work** — 6 projects, mixed services, links to `/work/`
5. **Why SPL** — certification, method, warranty, the "laboratory" proof points
6. **Brands we're certified in** — XPEL, Ceramic Pro, Revivify, ETG, DTE, Pro Tuning Freaks
7. **Reviews** — real Google review pull
8. **The shop** — location, hours, map, photos of the facility
9. **Quote form** — inline, not a link
10. **Footer** — full service index (SEO value), NAP, socials, financing

---

## 7. URL migration & redirect strategy

**Non-negotiable: every one of the 528 existing URLs must resolve.** A 404 on a ranking PPF page is a direct revenue loss.

### 7.1 Rules

| Source | Treatment |
|---|---|
| Real content pages (113) | **301** to new canonical equivalent |
| Portfolio `/project-details/*` (367) | **301** to `/work/[same-slug]/` — slug preserved to retain any equity |
| Vancity demo content (48) | **410 Gone** — never indexed as real content, do not redirect |
| Duplicate slugs across domains | All variants **301** to the single new canonical |
| Subdomain roots | **301** to the relevant new hub |
| WooCommerce system pages | Consolidate to one set, or remove — see Open Questions |

### 7.2 Sample mappings

| Old | New |
|---|---|
| `paintprotection.speedprojectslab.com/` | `/paint-protection/` |
| `paintprotection.…/paint-protection-film/` | `/paint-protection/ppf/` |
| `paintprotection.…/ppf-cost-vancouver/` | `/paint-protection/ppf/cost/` |
| `paintprotection.…/tesla-ppf-vancouver/` | `/paint-protection/ppf/tesla/` |
| `paintprotection.…/tesla-model-3-ppf-vancouver/` | `/paint-protection/ppf/tesla/model-3/` |
| `paintprotection.…/matte-stealth-ppf-vancouver/` | `/paint-protection/ppf/stealth-matte/` |
| `performance.speedprojectslab.com/` | `/performance/` |
| `performance.…/bmw-dme-unlock-service-richmond/` | `/performance/dme-unlock/` |
| `performance.…/track-prep-vancouver/` | `/performance/track-prep/` |
| `speedprojectslab.com/project-details/[slug]/` | `/work/[slug]/` |
| `vancitytires.com/tire-buying-guide/` | `/tires/buying-guide/` |
| `vancitytires.com/product/elegant-sunglasses/` | **410** |
| All `/about-us/` variants (3) | `/about/` |
| All `/contact-us/` variants (3) | `/contact/` |

*The complete 528-row redirect map is delivered as a separate CSV: **472 × 301**, **48 × 410**, **8 × 200** (paths that keep their existing URL on the main domain and simply receive 301s from the other properties). Verified for duplicate sources, malformed destinations, and redirect chains — all clean.*

### 7.3 Launch sequence

1. Build and stage the full site with redirects configured but not live
2. Verify every one of the 528 source URLs resolves (crawl the staging redirect map — expect 472 × 301, 48 × 410, 8 × 200)
3. Consolidate Google Search Console properties; submit change of address for each subdomain
4. Launch, keeping subdomain DNS live and pointed at the redirect layer **for a minimum of 12 months**
5. Submit the new sitemap; monitor Search Console coverage daily for 30 days
6. Update Google Business Profile, all citations, and social links to the new canonical URLs

---

## 8. Content strategy

### 8.1 Immediate

- **Deduplicate.** 26 duplicated paths collapse to one canonical each. Where versions differ, merge the strongest copy from each.
- **Rewrite the homepage.** It currently sells nothing.
- **Standardize NAP** across every page, schema block, and citation.
- **Add pricing ranges.** The PPF cost page exists but no service page carries a starting figure. Buyers filter on price whether or not you give them one — better they filter with your number than a competitor's.

### 8.2 Structural

- **Portfolio taxonomy.** Tag all 367 projects by *make*, *model*, *year*, *service(s)*. This powers gallery filtering, service-page proof modules, and generates long-tail landing pages ("Porsche PPF work," "BMW ECU tuning projects").
- **Service page template.** Every service page follows the same spine: what it is → who it's for → packages/tiers → starting price → our process → warranty → our work on this service → FAQ → quote form.
- **Blog, actually.** Three empty blog pages is worse than none. Either commit to a cadence — one post monthly, targeting the questions the sales team answers on the phone — or remove them.

### 8.3 Schema markup

`AutoRepair` / `LocalBusiness` with full NAP and hours · `Service` on each service page · `AggregateRating` for the 267 reviews · `FAQPage` on service FAQs · `BreadcrumbList` site-wide · `ImageObject` on portfolio entries.

---

## 9. Technical architecture

### 9.1 Framework recommendation — **Astro**

Given the repo choice, Astro over Next.js for this specific project:

| Consideration | Astro | Next.js |
|---|---|---|
| ~430 mostly-static pages | Ideal — zero JS by default | Works, heavier baseline |
| Core Web Vitals | Best-in-class; ships no JS unless asked | Good, but React runtime always loads |
| Image-heavy portfolio | Built-in `<Image>` with AVIF/WebP | Requires config or paid optimization |
| Build complexity | Lower | Higher |
| Team ramp-up | Simpler mental model | Requires React fluency |
| Islands for interactive bits | Native (filters, forms, menus) | Everything is React |

This is a marketing site with a gallery and some forms — not an application. Astro's output is faster, cheaper to host, and simpler to hand over. Interactive pieces (portfolio filter, quote wizard, mega-menu) run as islands.

*If SPL intends to build a customer portal, booking engine, or account system in-house later, Next.js becomes the better call. Flagged as an open question.*

### 9.2 Content management

The team needs to edit copy and add portfolio entries without touching code.

**Recommended: Sanity Studio** — free tier covers this scale, excellent image handling, structured content, real-time preview, hosted editing UI. Portfolio entries with make/model/service taxonomy model cleanly.

**Alternative: Keystatic** — git-based, no external service, zero cost, editing UI runs in the repo. Simpler, but no image CDN and weaker for non-technical editors.

**Not recommended: headless WordPress.** It preserves the familiar editor but keeps the maintenance burden the consolidation is meant to eliminate.

### 9.3 Stack

| Layer | Recommendation |
|---|---|
| Framework | Astro 5, TypeScript, static output |
| Styling | Tailwind CSS with design tokens from §10 |
| CMS | Sanity (hosted studio at `/admin`) |
| Images | Sanity CDN + Astro `<Image>`, AVIF/WebP, lazy below fold |
| Hosting | Vercel or Cloudflare Pages — both handle 500+ redirects natively |
| Forms | Server endpoint → email + CRM; spam protection via Turnstile |
| Booking | Depends on current system — see Open Questions |
| Analytics | GA4 + Search Console; consider Vercel Analytics for CWV |
| Repo | `DMCollective/spl` (currently empty except README) |

### 9.4 Performance budget

LCP < 2.0s · CLS < 0.1 · INP < 200ms · Initial JS < 50KB on content pages · Hero image < 200KB (AVIF) · Lighthouse ≥ 95 across all four categories.

### 9.5 Accessibility target — WCAG 2.1 AA

All text ≥ 4.5:1 contrast (large text ≥ 3:1) · full keyboard navigation with visible focus · alt text on all 367 portfolio images (a real content task, not a checkbox) · forms with associated labels and inline error messaging · `prefers-reduced-motion` respected on all scroll and hover animation.

---

## 10. Visual direction

Developed in full in the companion document **`SPL-Visual-Direction.md`**, and rendered as a working homepage in **`spl-homepage-concept.html`**.

**Summary — cinematic luxury.** The reference sites establish that dark, photography-led, full-bleed design is right for this category. The execution goes somewhere different from either of them: warm cinematic blacks rather than neutral greys, a letterboxed hero with a slow drift, a light serif display in sentence case rather than wide-tracked uppercase, platinum hairlines as the accent, and roughly double the usual vertical space between sections.

The reasoning is that a protected car looks like a car nobody has touched. The product is invisible when it's done right — so the design shows the car and gets out of the way. Density, chunky cards, and heavy accent colour work against that; restraint works for it.

**Red is held in reserve.** SPL's logo red spread across buttons, bands, and rules stops being a brand signal and becomes wallpaper. Used once per screen, on the one thing you want clicked, it is unmistakably SPL *and* the most conspicuous element on the page. On the homepage concept it appears exactly twice. Note the current logo red `#F31717` fails AA as a button fill with white text (4.25:1) — `#C4161C` at 6.04:1 replaces it for that role.

*(An earlier draft of this section followed the Rides Miami layout too literally and carried copy written for a tuning shop. It has been replaced. See `SPL-Visual-Direction.md` v2.)*

**Fixed constraints:**

- The 604 number and an enquiry route reachable at every scroll position
- Vehicle photography is the hero; the design gets out of its way
- Trust signals (5.0 ★, 267 reviews, XPEL certification, est. 2017) present but understated — set as captions, not badges
- Every colour pair clears WCAG AA — verified, not assumed

**Photography is the dependency.** The direction works with the existing library and becomes genuinely striking with twenty considered images. A half-day shoot covering the bay, two or three hero cars, and close detail of film going onto a panel is the highest-return line item in the project.

## 11. Open questions

| # | Question | Blocks |
|---|---|---|
| 1 | **Suite 401 or 403?** Which is the canonical business address? | NAP, schema, GBP, launch |
| 2 | **E-commerce** — three WooCommerce stores exist. Is online product sales a live channel, or vestigial? Keep, move to Shopify, or drop? | Architecture, scope |
| 3 | **Booking system** — what powers `/book-now/` today? Third-party (Booker, Setmore, Calendly) or a form? Keeping or replacing? | Integrations, forms |
| 4 | **Vancity Tires brand** — fold the brand in entirely, or keep `vancitytires.com` as a redirect to `/tires/` while retiring the separate identity? | IA, brand, redirects |
| 5 | **Analytics access** — GA4 and Search Console for all four properties, to set real baselines | Success metrics |
| 6 | **Photography** — is there a library of high-res shop and vehicle imagery beyond the portfolio, or is a shoot needed? | Visual direction, budget |
| 7 | **Pricing disclosure** — willing to publish starting-from figures per service? | Content, conversion |
| 8 | **Future portal** — any plan for customer accounts, service history, or an in-house booking engine? | Astro vs Next.js |
| 9 | **Blog commitment** — is there capacity for a content cadence, or should blog be removed? | IA |
| 10 | **Timeline & launch window** | Phasing |

---

## 12. Proposed phasing

| Phase | Scope | Output |
|---|---|---|
| **0. Discovery** *(current)* | Audit, IA, brief, visual direction | This document + redirect map |
| **1. Design** | Design system, homepage, service template, portfolio, contact/quote — desktop + mobile | Approved comps |
| **2. Foundation** | Astro scaffold, Sanity schemas, design tokens, component library | Working system, no content |
| **3. Content migration** | 113 pages deduped and rewritten; 367 portfolio entries imported and tagged | Populated staging site |
| **4. Redirects & SEO** | 528-row redirect map implemented and verified; schema; sitemaps | Verified crawl, zero 404s |
| **5. Launch** | DNS, GSC change of address, GBP and citation updates | Live |
| **6. Post-launch** | 30-day Search Console monitoring, CWV tuning, conversion tracking | Performance report |

---

## Appendix A — Sources

| Source | Reference |
|---|---|
| Main site | https://speedprojectslab.com/sitemap_index.xml |
| Paint Protection | https://paintprotection.speedprojectslab.com/sitemap_index.xml |
| Performance | https://performance.speedprojectslab.com/sitemap_index.xml |
| Vancity Tires | https://vancitytires.com/sitemap_index.xml |
| Design reference | https://www.moojoautospa.com/ |
| Design reference | https://www.weareridesmiami.com/ *(pending screenshots)* |

## Appendix B — Deliverables

- `SPL-Design-Brief.md` — this document
- `SPL-Redirect-Map.csv` — all 528 source URLs with destination and status code
- `spl-homepage-concept.html` — rendered homepage concept
- `SPL-Visual-Direction.md` — design system and visual direction

