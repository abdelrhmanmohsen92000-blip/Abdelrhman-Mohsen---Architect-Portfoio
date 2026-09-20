# CLAUDE.md — Abdelrhman Mohsen Personal Portfolio

> Context for Claude Code on this project. Read before making changes.

---

## 1. What this project is

A **premium, multi-page static portfolio site** for **Abdelrhman Mohsen**, BIM Architect &
Architectural Designer. Architecture:

- `index.html` — the main one-page scroll site (nav, hero, 15 numbered sections, footer).
- `work/*.html` — six dedicated case-study pages (one per flagship project), each following the
  same 01–07 structure (Overview, Challenge, Approach, BIM Workflow, Visual Development,
  Technical Delivery, Outcome).
- `styles.css` — shared design system for every page (homepage + all case studies).
- `script.js` — shared behavior for every page (nav, scroll-reveal, animated stat counters,
  gallery filter tabs, lightbox, contact-form mailto).
- `img/` — all imagery, extracted from the two source PDFs (see §2).

No build step, no framework. This was a **full redesign** (2026-09-20) superseding an earlier,
simpler single-page "dark blueprint" version — the user supplied a detailed premium-portfolio
brief (architectural editorial aesthetic, stone/charcoal/bronze palette, case-study pages, a
specific 15-section structure) and this is that rebuild. If asked to touch "the old version",
there isn't one kept around — this *is* the current site.

This is a **sister project** to the TAFKEEK studio website (separate repo, not here) and to
Abdelrhman's own earlier personal-site concept. Keep this one visually distinct from TAFKEEK's
warm/editorial cream-charcoal-brass look — this site's palette is closer in hue (bronze/charcoal
appear in both) but the layout language, typography (Inter only, no serif display font) and
overall system are different and should stay that way.

---

## 2. Source of truth for all content

Everything must trace back to:

- `Abdelrhman_Mohsen_BIM_Architect_CV.pdf` — summary, education, experience, skills, software,
  languages, the six "Selected Projects" with their real facts (area, scope, discipline).
- `Abdelrhman_Mohsen_BIM_Architect_Portfoilo.pdf` (37-page deck) — about/stats, skill categories,
  and every image in `img/`.

**Never fabricate bio details, job history, stats, project facts, locations or years.** Where a
fact isn't in the source (e.g. La-Mer Compound's location, or a year for most of the six
projects), the site says "Not specified in source" or simply omits the field — it does not
guess. See the CV header's `Portfolio@google.com` — a broken/placeholder field, never used as a
real contact method.

### Important: image-to-project attribution is NOT verified for 4 of the 6 case studies

Only **Square Business Hub** has a portfolio-deck image explicitly captioned with that project's
name, area and year — its hero/visual images are a confirmed match. For **La-Mer Compound,
Lamar Gate, Meydan Villa, Royal Meadows and Supply Chain — Riyadh**, no portfolio-deck image is
named as belonging to that specific project, so their pages use other real (not fabricated)
portfolio images captioned as "representative" — e.g. "Representative BIM deliverables from the
same modeling and coordination workflow" or "Representative villa exterior render". This is
stated explicitly in the Selected Work section intro on the homepage and again in each affected
case study's "05 — Visual Development" section. **Do not remove these disclosures or silently
re-caption a representative image as if it depicts the specific named project** — that would
reintroduce the fabrication the disclosures exist to avoid. If real, confirmed photography for
these five projects becomes available, replace the representative images and delete the
disclosure sentence for that project only.

Also note: there is no "Kitchen" photo in the source material despite "Dining & Kitchen" being a
slide title in the deck — the only real photo on that slide is the dining room. An image
originally miscropped as "kitchen" was renamed to `int-styling-detail.jpg` and is not used with
a Kitchen label anywhere on the site.

---

## 2b. Image sourcing (updated 2026-09-20, second pass)

The first pass's images (full-slide crops from the portfolio PDF, baked-in caption bars) read as
low-rhythm and unpolished, so `img/` was rebuilt from two folders the user placed directly in
this project directory:

- `WEB PORTFOLIO/` — a prior, already-built version of this exact site (see
  `WEB PORTFOLIO/files/abdelrhman-portfolio/Abdelrhman-portfolio/index.html`), with a clean,
  individually-cropped `img/` set (no baked captions, real single-subject photos) plus a video
  walkthrough (`modern-facade.mp4`) and a proper portrait crop (`profile.webp` /
  `profile-og.jpg`). This is now the primary image source — copied wholesale into `img/`, and the
  old PDF-slide-dump crops were deleted. Its HTML was also used as a reference for animation
  patterns (the `reveal` / `reveal-left` / `reveal-right` / `reveal-scale` variety in `styles.css`
  and `script.js`) and for tighter copy in the About section.
- `Designs/` — a larger raw render dump (270 files, mostly numeric filenames, no captions).
  Reviewed via generated contact sheets (deleted after review) and selectively mined — see §6c.

## 6c. Fourth pass — mining `Designs/` for confirmed real content (2026-09-20)

The user asked to use images from `Designs/`. Reviewing all 270 files (via contact sheets)
surfaced two major finds that materially improved credibility over the "representative image"
disclosure used elsewhere:

- **`Designs/Details/Supply chain/`** — the actual issued-for-tender drawing set for the CV's
  "Supply Chain — Riyadh" project. Titled on the drawings themselves: **"Supply Administration
  Building & its Related Services"**, owner **King Saud Medical City**, consultant Al-Shabana Co.,
  status "Issued for Tender". Copied in as `bim-supplychain-elev-north.jpg`,
  `bim-supplychain-elev-east.jpg`, `bim-supplychain-plan-ground.jpg` (cold storage/quarantine/
  loading bay), `bim-supplychain-plan-offices.jpg`, `bim-supplychain-detail-wall.jpg`. The
  `work/supply-chain-riyadh.html` case study was rewritten around these — no more "representative"
  disclosure for this project, the meta grid now shows the real Owner/Status fields, and one of
  these replaced a generic image in the homepage's Technical Documentation section too.
- **`Designs/Building B+A Cam 01-06.jpg`** — real renders with "LAMAR BUSINESS PARK" visible on
  in-render signage, closely matching the CV's "Lamar Gate" project by name. Copied in as
  `ext-lamar-business-park-1/2/3.jpg` and used as the Lamar Gate case study hero + homepage
  thumbnail, with the disclosure text updated to state plainly that this is "Lamar Business Park"
  (the name on the signage) rather than asserting full identity with "Lamar Gate."
- **`Designs/1 (6).jpg`** — a real kitchen render, filling the gap noted in §2b (no true kitchen
  photo existed before). Added as `int-kitchen-real.jpg` to the Interior gallery.
- A few more real pieces added to the Architecture gallery for variety:
  `ext-commercial-night-gold.jpg` (a night facade render, "Abdelrhman Mohsen" watermark visible —
  clearly his own work) and `ext-pavilion-concept-1.jpg` (an organic parametric massing study,
  SketchUp clay-render style — captioned explicitly as a "Concept Massing Study / Early Design
  Stage" since its render style differs from the photoreal pieces around it; don't relabel it as
  a finished render).

**Excluded on purpose**: files named `create_same_image_202603/202604*` and
`add_seating_woman/women_202603*` in `Designs/` — the filenames strongly suggest AI-generated or
AI-edited variations of other images, not original render/CAD output. Do not use these as
portfolio content without first confirming their actual provenance with the user. Also skipped:
`Test 1.jpg` / `Test 2.jpg` (ambiguous), and straightforward duplicates already covered by the
`WEB PORTFOLIO` set.

Not yet mined: `Designs/Details/Salman Villa/`, `Bandar Villa/`, and `classic ethmar/` also
contain real named-project technical drawings (mostly PDFs) — not used this pass since none of
those names match a CV-listed project, but they're real private-client work if more technical
documentation variety is wanted later. Don't assume "Salman Villa" = "Meydan Villa" without
confirming with the user first — it's a plausible but unverified guess.

Neither folder is part of the deployable site — don't reference paths inside them from HTML;
copy any image you want to use into `img/` first (and note here what was added).

## 3. Images (`img/`)

Almost all images are now `.webp` from the `WEB PORTFOLIO` reference set (see §2b) — clean,
individually cropped, no baked-in captions. Naming: `bim-*` (documentation, coordination,
schedules), `ext-*` (exterior/landscape), `int-*` (interior), plus `profile.webp` /
`profile-og.jpg` (portrait), `model3d.webp` / `exploded.webp` / `floorplan.webp` /
`elevation.webp` / `schedule.webp` / `cde.webp` / `navisworks.webp` (single-purpose BIM visuals),
and `modern-facade.mp4` + `modern-facade-poster.webp` (the Architecture section's featured video).

`favicon-*.png` / `favicon.ico` are the generated "AM" monogram from the first pass, not from
either source folder — kept as-is.

The handful of `.jpg` files still in `img/` (`ext-hero.webp` is `.webp`, not `.jpg` — check the
actual extension before assuming) are leftovers worth checking against the current file listing
if this section ever goes stale; when in doubt, `Get-ChildItem img` is the source of truth over
this list.

---

## 4. Shared systems

- **Design tokens**: `styles.css` `:root` — stone/paper/cool-gray backgrounds, charcoal text,
  bronze accent. Sharp corners (`--radius: 2px`), no heavy rounding, no gradients beyond the
  hero's dark overlay. Large `display-*` type classes carry the "typography as a major visual
  element" requirement — don't shrink headings to fit content, adjust the layout instead.
- **Gallery filter**: `data-tabs-for="#gallerySelector"` on a `.gallery-tabs` bar + `data-group`
  on each `.gallery-item` — same safe pattern used on the TAFKEEK site. A new gallery item needs
  a `data-group` or the filter hides it.
- **Lightbox**: any element wrapped in `[data-lightbox-scope]` with children carrying
  `data-lightbox` + `data-caption` becomes a lightbox group; arrow keys/swipe navigate only the
  *visible* (post-filter) items in that scope. Every page includes its own `#lightbox` markup at
  the end of `<body>` (kept per-page, not injected by JS) — copy that block when adding a page.
- **Reveal-on-scroll**: add class `reveal` to any element; `script.js` adds `in-view` via
  IntersectionObserver. Respects `prefers-reduced-motion`.
- **Animated counters**: `data-count="150K+"` etc. on an element with initial text `0` — parses
  prefix/number/suffix and counts up once when scrolled into view.
- **Contact form**: `#inquiryForm` has no backend (static site) — `script.js` builds a `mailto:`
  link from the field values on submit. If the user wants real form submissions, that needs a
  form service or backend added explicitly (ask first — third-party integration).

---

## 5. Case-study pages (`work/`)

Six pages, each following the section numbering 01–07 from the brief. Files:
`la-mer-compound.html`, `lamar-gate.html`, `square-business-hub.html`, `meydan-villa.html`,
`supply-chain-riyadh.html`, `royal-meadows.html`. Each links to the next in a loop via the
"Next Project" panel at the bottom — keep that chain intact if a page is added or removed.
Paths inside `work/` are relative (`../styles.css`, `../img/...`, `../index.html#section`).

---

## 6. Contact info

- **Email:** `architect.abdelrhmanmohsen@gmail.com` (personal — different from TAFKEEK's
  `studiotafkeek@gmail.com`, do not conflate).
- **Phone / WhatsApp:** `+20 109 208 3829`.
- **LinkedIn:** `linkedin.com/in/abdelrhman-mohsen-bimarchitect`.

---

## 6b. Third pass — refinement, not rebuild (2026-09-20)

The user's third round of feedback was an explicit "upgrade pass, do not rebuild" brief. Changes
made in that pass, on top of the second-pass rebuild in §2b:

- Nav simplified: `Work · BIM · Design · About · Capabilities · Contact` (dropped the separate
  "Interior" link — the Interior section still exists and is reached by scrolling past
  Architecture; only the nav entry was consolidated).
- Hero: name (`ABDELRHMAN MOHSEN`) is now the largest, most prominent element, with
  `BIM ARCHITECT · ARCHITECTURAL DESIGNER · BIM COORDINATOR` as a smaller line below it. Added
  the "Design. Coordinate. Deliver." brand line once (hero top-line only — don't repeat it
  elsewhere, the brief was explicit about not overusing it). Softened the technical annotation
  overlays (opacity 0.4, smaller). Added a subtle animated scroll indicator (`.hero-scroll`,
  hidden under 640px). Hero CTA is now "View BIM & Technical Work" / "Start a Project" — the
  dual for-companies/for-clients path referenced in §30 of that brief.
- Selected Work: split into "Featured Projects" (La-Mer Compound, Square Business Hub — the two
  with the strongest verified metrics) as large editorial cards (`.featured-grid` /
  `.featured-card`), and "Selected Work" for the remaining four as the existing list rows. No
  projects were removed.
- Clash Detection: the before/after comparison previously showed the same image twice via a
  CSS split-crop trick (technically showing genuine different halves, but reads as suspicious).
  Replaced with a single full-width image and an honest caption
  ("MEP Terminals vs. Pipes — Before (left) / After Coordination (right)") — same real asset,
  no more dual-`<figure>` duplication.
- Contact headline changed to "Let's build something well coordinated." (from "...great.");
  added a supporting line. CTA section buttons reframed as
  For Companies → View BIM & Technical Work / For Clients → Start a Project, with
  Download CV / View LinkedIn kept as secondary actions.
- Accessibility: added `:focus-visible` outlines (bronze, 2px) site-wide — this was missing
  before and is a real gap the brief's §34 flagged generically; now fixed.

Not changed in this pass (already compliant or out of scope for a refinement): color palette,
typography choice, BIM Capabilities column order, Why-Work-With-Me card styling (already
sharp-cornered, not "generic rounded cards"), case-study page structure (already matches the
Overview/Challenge/Approach/Workflow/Visuals/Delivery/Outcome shape asked for), contact form
(still `mailto:`-only by design — no fake backend was added).

## 6d. Fifth pass — polish audit, no redesign (2026-09-20)

The user asked explicitly for polish only: image-to-project credibility audit, case-study
consistency, responsive/performance, contact-form audit — no visual redesign. Findings and fixes:

- **Image/project conflicts found and fixed**: two project cards were illustrated with *another
  confirmed real project's* photo, which is worse than a generic placeholder — it implies the
  wrong project looks like a different specific, named one. Fixed both (homepage thumbnail +
  case-study hero + visual grid in each case):
  - Meydan Villa was using `ext-villa-classical.webp`, which is **M3MAR Villa** (confirmed, Qatar,
    600 m² — captioned as such in the Architecture gallery two sections up on the same page).
    Swapped to `ext-villa-classical-day.webp`, which carries no proper project name anywhere else
    on the site.
  - Royal Meadows was using `ext-pool-landscape.webp`, which is **ESTRA7A**'s real pool/landscape
    photo (confirmed, captioned as such elsewhere). Swapped the hero and visual-grid slot to
    `ext-masterplan-aerial.webp` (thematically apt for a large-scale park, and — same check — not
    tied to a specific named project anywhere else on the site).
  - Before reusing any image for a new spot, grep the rest of the site for that filename and check
    whether it's captioned with a specific project name elsewhere — that's the actual audit
    procedure, not just "is this a real photo."
- **Wording tightened where the underlying asset is genuinely confirmed real**: Lamar Gate's
  "05 — Visual Development" was hedging on all four images equally, when three of the four are
  real confirmed Lamar Business Park renders (signage visible in-frame) and only the *La Mer Gate
  = Lamar Business Park identity claim* is the actual uncertainty. Reworded to say the renders
  are real plainly, and confine the hedge to the identity question only. Square Business Hub and
  Supply Chain — Riyadh were already stated directly (no lingering "representative" language to
  remove there).
- **Case-study nav was stale on all six pages** — still had the old `Architecture` + `Interior`
  two-link nav and was missing `Capabilities`, from before the third-pass nav consolidation on
  the homepage. Synced all six to match `index.html` exactly:
  `Work · BIM · Design · About · Capabilities · Contact`.
- **Contact form audited**: confirmed (again) it is `mailto:`-only — `script.js` builds a
  `mailto:` URL and does `window.location.href = mailto`; there is no `fetch`/`XHR` anywhere, no
  third-party form service. It does **not** submit anything itself — it opens the visitor's own
  mail client with a pre-filled draft they still have to send themselves, and does nothing useful
  for a visitor with no configured mail client. The button previously read "Send Project Inquiry"
  with no indication of this — added a small note under the button explaining what actually
  happens. Did not add a fake/simulated "success" state and did not wire in a real backend without
  being asked.
- **Performance**: found zero `loading="lazy"` anywhere despite ~75 images on the homepage alone,
  meaning every gallery image (BIM/Architecture/Interior/Technical Documentation/Design+BIM
  compare, ~70+ images) was fetched eagerly on page load regardless of scroll position. Added
  `loading="lazy"` to every `<img>` site-wide except each page's hero background image, which
  instead got `fetchpriority="high"` (it's the LCP element). Verified via network log: homepage
  now fires ~6 requests on initial load instead of 70+.

Not changed (already fine / explicitly out of scope for this pass): color palette, typography,
section structure, case-study 01–07 format, hero layout, any copy not flagged above.

## 6e. Sixth pass — homepage curation + performance, no redesign (2026-09-20)

The homepage was carrying the *entire* portfolio (BIM 19 images, Architecture 15 + video,
Interior 17, Technical Documentation 6 = ~57 gallery images alone, all eager-loaded). The user
asked for a curated homepage with full galleries moved to dedicated pages, not a redesign.

- **New dedicated pages** (`work/`): `bim-portfolio.html`, `architecture-portfolio.html`,
  `interior-portfolio.html`, `technical-documentation.html`. Each holds the **complete** original
  gallery (all images, all filter tabs, same lightbox pattern) that used to be on the homepage —
  nothing was deleted, only relocated. Same nav/footer/lightbox scaffold as the case-study pages.
- **Homepage galleries trimmed** to curated subsets, each followed by a "View Full X Portfolio →"
  link to its dedicated page:
  - BIM: 19 → 6 (floor plan, 3D model, exploded axo, Navisworks, one clash comparison, schedule —
    one representative image per category so the preview still reads as complete workflow, not a
    random sample).
  - Architecture: 15 → 6 (Square Business Hub, Villa 108, M3MAR Villa, ESTRA7A, master plan
    aerial, night facade — spans modern/classical/masterplan).
  - Interior: 17 → 6 (Yasser Villa suite, bathroom, kitchen, contemporary living, Sara dining,
    private office — spans modern/neoclassic/commercial).
  - Technical Documentation: 6 → 3, per explicit instruction (Floor Plan / Facade &amp; Wall
    Detail / Shop Drawing).
  - Filter tabs were removed from the *homepage* curated grids (6 items don't need filtering) but
    kept on all four dedicated full-portfolio pages.
  - Dropped the `wide` grid-span class from the curated 6-item sets — with only 6 items a uniform
    3-col grid (2 clean rows) reads better than the dense/wide layout built for 15+ items, which
    left an awkward half-empty row at that count.
- **Thumbnails** (`img/thumbs/*.jpg`, ~29 KB average vs. 150–450 KB originals): every gallery grid
  image everywhere (homepage curated sets *and* the four full-portfolio pages) now displays a
  560px-wide JPEG thumbnail; the original full-resolution file only loads when the lightbox opens
  (via `data-full` on the `[data-lightbox]` element — `script.js`'s `render()` already preferred
  `dataset.full` over the `<img>` src, so no JS change was needed there, just adding the
  attribute). Generated via WPF/WIC (`System.Windows.Media.Imaging`), not GDI+ — .NET's
  `System.Drawing` **cannot decode `.webp`** (throws a misleading "Out of memory" from
  `Image.FromFile`), but the WPF imaging stack can. If more thumbnails are needed later, reuse
  that approach, not `System.Drawing`.
- **`loading="lazy"` + `decoding="async"`** applied to every `<img>` site-wide except each page's
  hero background (which gets `fetchpriority="high"` instead — it's the LCP element).
- **Video lazy-load**: the featured video (`modern-facade.mp4`) no longer has `autoplay`/eager
  `src`. It's `<video data-src="...">` with `preload="none"`; `script.js` has a new
  IntersectionObserver block (`video[data-src]`) that sets `.src` and calls `.play()` only once
  the video scrolls within 25% of the viewport, and `.pause()`s it when it scrolls back out. Same
  mechanism on the homepage (`#architecture`) and the dedicated Architecture portfolio page.
- **`defer`** added to every page's `<script src="script.js">` tag (was already effectively
  non-render-blocking from being at the end of `<body>`, but this makes it explicit).
- **Measured result** (verified via the browser's network log, not estimated): homepage now
  fires **5 requests before any scroll** (HTML, CSS, hero image, video poster, JS) versus roughly
  70 before this pass. Total `<img>` element count on the homepage dropped from 75 to 39.

If curating a homepage gallery further in future, the pattern to follow: pick images that already
have real/confirmed status (see §6d) where possible, keep one example per filter category so the
preview doesn't feel arbitrary, and always add the image to (not remove it from) the matching
dedicated full-portfolio page first.

## 7. Pending items

- [ ] `og:url` + JSON-LD `url` left empty on every page — fill in only once there's a real live
      URL. Do not invent one.
- [ ] No deployment target confirmed yet (no GitHub repo initialized for this project, unlike
      TAFKEEK's GitHub Pages setup).
- [ ] Contact form is `mailto:`-only (no backend), audited and disclosed in the UI as of §6d —
      confirm with the user before wiring in any third-party form service.
- [ ] Three of six case studies (La-Mer Compound, Meydan Villa, Royal Meadows) still use
      representative (not project-specific) imagery — see §2 and §6d. Swap in real photography if/
      when the user provides it. (Square Business Hub, Lamar Gate and Supply Chain — Riyadh are
      now backed by confirmed real project imagery, see §2b/§6c.)

---

## 8. Working style

- Prefer small, surgical edits over rewrites once the site is stable.
- After any change: verify images resolve, nav anchors resolve (including cross-page `work/*.html`
  → `../index.html#section` links), `rel="noopener"` on external links, gallery filter + lightbox
  behave, mobile layout holds (~390px) and desktop holds, no console errors.
- Site language is English (`<html lang="en">`).
