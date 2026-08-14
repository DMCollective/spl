# Speed Projects Lab — Visual Direction & Design System
**Companion to the Design Brief · v2 · August 14, 2026**

> **v2 supersedes v1.** The first pass leaned too literally on the Rides Miami reference and produced something that read as a copy rather than a direction — and its copywriting was written for a tuning shop, not a PPF studio. This version starts from the brief that matters: **cinematic luxury, for enthusiasts who want to protect their cars.**

---

## 1. The idea

A protected car looks like a car nobody has touched. That's the whole product — the work is invisible when it's done right. So the design shouldn't shout about the work; it should show the car and get out of the way.

The reference points are film and luxury goods, not automotive-services websites:

- **Letterboxing and grade.** Cinematic black bars, deep vignettes, a slow drift on the hero. Warm blacks and warm off-whites — pure `#000` and pure `#FFF` read as *screen*; warm reads as *film*.
- **Restraint with colour.** Near-monochrome, with one metal tone (platinum) doing the accent work. SPL red is held in reserve and spent on exactly one thing: the primary action.
- **Editorial type.** A light serif at large sizes, mixed case. Confidence is quiet. Wide-tracked uppercase everywhere is the opposite of luxury — it's what a performance parts catalogue does.
- **Space.** Fewer sections, more air. A luxury site's most expensive-looking asset is the emptiness around the content.

**What this is not:** dense card grids, chunky arrow-block buttons, skewed red bands, or "PROTECT · PERFORM · ROLL." Those were the v1 mistakes.

---

## 2. Colour

```css
/* Cinematic base — warm blacks, never neutral grey */
--black:        #08090A;
--surface:      #0F1113;
--elev:         #16181B;
--hairline:     rgba(200,191,174,.14);
--hairline-soft:rgba(200,191,174,.07);

/* Warm off-white — this is what reads as film rather than screen */
--bone:         #EDEAE5;   /* 16.61:1 on black */
--muted:        #A6A199;   /*  7.76:1 on black */
--platinum:     #C8BFAE;   /* 10.93:1 on black — the accent */

/* SPL red. Reserved. One job. */
--red:          #C4161C;   /* white on it: 6.04:1 */
--red-deep:     #B01216;   /* white on it: 7.13:1 — hover */
--red-lift:     #FF5A5F;   /* red as TEXT on black: 6.53:1 */
```

### Why red barely appears

SPL's logo red is `#F31717`. Spread across buttons, bands, headings and rules — as in v1 — it stops being a brand signal and becomes wallpaper. Used once per screen, on the one thing you want clicked, it does two jobs at once: it's unmistakably SPL, and it's the most conspicuous element on the page.

On the homepage concept, red appears exactly twice: the *Request a Quote* button, and the mobile *Enquire* bar. Everything else is bone, muted, and platinum.

Note that `#C4161C` on black is **3.30:1** — fine as a large graphic element or a filled button with white text, but **not usable as red text on a dark background**. For that, `--red-lift` `#FF5A5F` (6.53:1) exists. Same reasoning as v1: one brand red, three functional roles.

### Verified pairings

| Foreground | Background | Ratio | |
|---|---|---|---|
| `--bone` | `--black` | 16.61:1 | AAA |
| `--bone` | `--surface` | 15.77:1 | AAA |
| `--platinum` | `--black` | 10.93:1 | AAA |
| `--platinum` | `--elev` | 9.76:1 | AAA |
| `--muted` | `--black` | 7.76:1 | AAA |
| `--muted` | `--elev` | 6.93:1 | AA |
| White | `--red` | 6.04:1 | AA |
| White | `--red-deep` | 7.13:1 | AAA |
| `--red-lift` | `--black` | 6.53:1 | AA |
| `--black` | `--platinum` | 10.93:1 | AAA |

Focus rings use `--platinum` at 10.93:1 — well past the 3:1 non-text requirement. Hairlines are decorative only and never carry state.

---

## 3. Typography

| Role | Face | Why |
|---|---|---|
| Display | **Cormorant Garamond** — 300, 400, and 300 italic | High-contrast serif. At 60–100px in light weight it reads editorial and expensive. This is the single biggest lever in the whole direction. |
| Everything else | **Inter** — 200, 300, 400, 500 | Clean, quiet, disappears. Carries eyebrows, nav, body, labels, buttons. |

### Scale

| Role | Face | Size | Weight | Case | Tracking |
|---|---|---|---|---|---|
| H1 | Serif | `clamp(44px, 7.4vw, 104px)` | 300 | Sentence | `-0.015em` |
| H2 | Serif | `clamp(32px, 4.6vw, 62px)` | 300 | Sentence | `-0.015em` |
| H3 | Serif | `clamp(22px, 2.2vw, 30px)` | 400 | Sentence | normal |
| Pull quote | Serif italic | `clamp(24px, 3.3vw, 44px)` | 300 | Sentence | `-0.01em` |
| Eyebrow | Sans | 11px | 400 | UPPER | `0.36em` |
| Nav | Sans | 11px | 300 | UPPER | `0.22em` |
| Button | Sans | 12px | 400 | UPPER | `0.24em` |
| Lede | Sans | `clamp(16px, 1.35vw, 19px)` | 300 | Sentence | normal |
| Body | Sans | 17px / 1.85 | 300 | Sentence | normal |
| Label / caption | Sans | 10–12px | 400 | UPPER | `0.24–0.28em` |

**The rule:** serif is only ever sentence case, only ever large, only ever light. Sans is only ever small. Nothing lives in between — that middle ground is where sites start looking generic.

**Emphasis** inside a headline is italic serif in `--platinum`, never bold and never red.

Both faces self-hosted as variable WOFF2, Latin subset, `font-display: swap`.

---

## 4. Space & layout

| | |
|---|---|
| Container | 1240px, 32px gutters (22px mobile) |
| Section rhythm | `clamp(88px, 11vw, 180px)` — roughly double a conventional marketing site |
| Radius | **0 everywhere** |
| Elevation | No shadows. Depth is `--black` → `--surface` → `--elev` plus platinum hairlines. |
| Dividers | 1px `--hairline-soft`. Content sits on rules rather than inside boxes. |
| Breakpoints | 640 · 1080 · 1240 |

Services are **editorial rows** — alternating image/text, separated by hairlines — not a card grid. Cards fragment attention; rows read like a magazine spread, and they let each service have a real photograph at scale.

---

## 5. Motion

| | |
|---|---|
| Easing | `cubic-bezier(.16, 1, .3, 1)` — slow out, long tail |
| Hero drift | 26s scale 1.06 → 1.16 with slight translate, infinite alternate |
| Image on hover | scale 1.05 over 1.4s, brightness lifts slightly |
| Section reveal | 26px rise + fade, 1.1s, `IntersectionObserver`, fires once |
| Button fill | Platinum panel wipes up from below over 600ms; label inverts to black |
| Header | Transparent over the hero, condenses to 76px with blur on scroll past 80px |

Everything is slower than a typical marketing site. Speed reads as cheap here; the pacing is doing as much work as the palette.

`prefers-reduced-motion: reduce` disables all of it — transitions, reveals, the hero drift — and shows content in its final state.

---

## 6. Components

**Button** — outlined in platinum, 19px/42px padding, 12px caps at `0.24em`. Hover wipes a platinum panel up from below and inverts the label to black. The solid variant is red-filled and exists once per page.

**Quiet link** (`.q-link`) — 11px platinum caps followed by a 28px rule that extends to 52px on hover. This replaces v1's arrow-block. It's the site's most-repeated element and the closest thing to a signature.

**Eyebrow** — 11px platinum caps at `0.36em`, no rule, sitting above a serif heading. The tracking does the work.

**Marque strip** — the makes SPL works on, set in light serif caps, sitting on `--surface` between hairlines directly under the hero. Instant credibility, zero images, and it answers "do they work on my car" in the first scroll.

**Service row** — alternating 1fr/1fr, roman numeral in serif platinum, serif H3, one paragraph, a tag list, and a quiet link. Image at 5:4.

**Cinematic band** — full-bleed image at `brightness(.34)` behind a left-weighted gradient, min-height 78vh. One per page.

**Work tile** — 3:4 portrait (one 3:2 wide per row), image at `brightness(.66)` darkening to `.42` on hover, serif vehicle name and platinum service caps over a bottom gradient. 6px gutters — nearly touching, like contact sheet frames.

**Pull quote** — centred italic serif at up to 44px, platinum stars above, attribution in micro-caps. One review, given real space, beats three in boxes.

**Form field** — no box. Transparent, with a single hairline underneath that turns platinum on focus. Label above in 10px caps.

---

## 7. Photography

This is the highest-leverage item in the project and the one thing the design cannot fix on its own.

| | |
|---|---|
| Grade | `brightness(.34–.72)`, `contrast(1.08–1.15)`, `saturate(.55–.72)`. Consistent across the library — this is what makes 367 phone photographs look like one body of work. |
| Hero | Full-bleed video where available. Slow, close, shallow. A squeegee crossing a fender is a better hero than a parked car. |
| Crops | 3:4 for work tiles, 5:4 for service rows, full-bleed for bands. |
| Format | AVIF primary, WebP fallback, `srcset` at 640/1024/1600/2400. Hero under 200KB. |
| Alt text | All 367 portfolio images need real alt text — vehicle, year, service. Budget for it as a content task. |

**Recommendation:** commission one proper shoot. Half a day with a photographer who understands automotive lighting, covering the bay, two or three hero cars, and detail shots of film going on. The direction works with the existing library; it becomes genuinely striking with twenty considered images.

**Never:** stock photography, lens flares, text baked into images.

---

## 8. Voice

The v1 copy was wrong and worth naming: *"Protect it. Sharpen it. Keep it that way."* — "sharpen" belongs to a tuning shop. SPL is a protection studio that also happens to tune.

The voice is **specific, calm, and slightly understated.** It assumes the reader already loves their car and doesn't need convincing that it's worth protecting.

| Do | Don't |
|---|---|
| "Some cars deserve to stay perfect." | "Unmatched vehicle excellence" |
| "Invisible while it's on. Obvious the day you sell." | "Premium quality protection solutions" |
| "Wrapped past the edges so there's no visible line." | "State-of-the-art techniques" |
| "This is the step most places skip." | "We go the extra mile" |
| "Three hundred and sixty-seven cars." | "Hundreds of satisfied customers" |

Numbers over adjectives. Concrete detail over claims. Never exclamation marks. Never "unmatched," "unrivaled," "top-tier," or "one-stop shop."

---

## 9. What's in the concept

`spl-homepage-concept.html` — a working, responsive homepage rendering this system end to end, using SPL's own photography.

Sequence: header → letterboxed hero → marque strip → statement → four service rows → cinematic band → work grid → pull quote → the other divisions → enquiry → footer.

Verified at 390 / 768 / 1440 / 1920: no horizontal overflow, no tap target under 24px, no image without alt text, no unlabelled form field, no console errors, reduced-motion honoured.

---

## 10. Your calls

1. **The serif.** Cormorant Garamond is the boldest choice here and the main thing that makes it read cinematic rather than corporate. If it feels too editorial for the enthusiast audience, the alternative is a very light wide sans (Jost or Archivo at 200) — same restraint, more machined. Say the word and I'll show both side by side.
2. **Hero video.** The concept uses a still with a slow drift. Real footage of film going onto a panel would be substantially better. Do you have any, or should we shoot?
3. **How far back does red go?** Currently it's on one button. If you want more brand presence I can bring it into the eyebrows and rules — but I'd argue against it.
4. **Photography.** Willing to fund a half-day shoot? It's the difference between good and genuinely striking.
