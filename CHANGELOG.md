# build.samrahim.com — Build Log

## Skills & Rules Applied

### Visual Taste Framework
Source: `visual-taste-SKILL.md`

Core principles used throughout:
- **Earned over Applied** — No faux-distressed textures. The grid pattern earns its place as a workshop measurement grid. Paper noise is kraft paper, not decoration.
- **Material Honesty** — Colors reference real materials: walnut (wood), brass (hardware), oxide (rust), parchment (kraft paper). Nothing pretends to be something else.
- **Warm Palette, Grounded** — `--parchment: #F5F1E8`, `--walnut: #2C2416`, `--brass: #8B7355`, `--oxide: #A65D3F`, `--graphite: #4A4A4A`. No gray-beige hedging.
- **Texture as Signature** — Grid background pattern + paper noise are the DNA. One strong texture reference (the measurement grid) anchors everything.
- **Confident Specificity** — Design world: **Mid-century American Workshop**. Grid = measurement marks on the workbench. Oxide = rust on tools. Walnut = the bench. Brass = hardware. Parchment = kraft paper.
- **One Bold Move, Not Five** — Oxide (#A65D3F) is the structural accent. CTAs, dividers, hover states. Everything else stays quiet.
- **European Leisure Register** — Unhurried, golden-hour energy. Playfair Display serif headlines. Generous whitespace.
- **Curated, Not Collected** — Every element is intentional. No clip art, no stock illustration, no emoji decoration.

### Design Decisions
- **Typography**: Playfair Display (serif headlines) + IBM Plex Mono (body/monospace)
- **Button hover**: Deeper oxide (#8B4A30), not walnut — walnut reads as black and kills the warmth
- **Letter-spacing**: Standardized to two values: `0` (body) and `0.1em` (uppercase labels only)
- **Transitions**: Specific properties (color, background-color, transform, border-color) instead of `transition: all`
- **Paper noise**: Opacity at ~0.45 — enough to feel like kraft paper, not distracting

### Custom Site Details (Not-Template Signals)
1. **Custom cursor** — Crosshair SVG (circle + crosshairs in walnut color)
2. **Selection color** — Oxide background with parchment text on highlight
3. **Ruled-line form inputs** — Bottom-border only, like lines on paper
4. **SR monogram** — Playfair Display italic in footer, low opacity
5. **Maker's mark footer** — "Built by me in The Sunshine State"

---

## Changelog

### 2026-02-01 — Portfolio Update: Calling Card In, LawnHQ Out
- Added Calling Card (Founder) — "Custom, one-page personal websites. Delivered in days, not weeks."
- Removed LawnHQ from portfolio
- Back to clean 2x2 grid: Haul, Calling Card, Pickleball State, JNKML Mailing Club

### 2026-02-01 — Mobile Optimization
- Added small-phone breakpoint at 400px (iPhone SE): tighter padding (16px), smaller hero (1.75rem), reduced section spacing
- Fixed touch targets to 44x44px minimum: nav CTA, modal close button, testimonial dots
- Made modal scrollable on mobile (`max-height: 80vh`, `overflow-y: auto`, `-webkit-overflow-scrolling: touch`)
- Fixed iOS form inputs: `-webkit-appearance: none`, `font-size: 16px` to prevent auto-zoom
- Bumped section labels from 0.6875rem to 0.75rem on mobile
- Increased lever label from 0.5rem to 0.625rem on mobile
- Added `overflow-wrap: break-word` to container to prevent text clipping on narrow screens

### 2026-02-01 — Rotating Testimonials
**Commits:** `6666fee`, `0cfb69e`, `51e9927`

- Added testimonial section after The Studio (before Portfolio) — optimal placement for social proof
- Two testimonials auto-rotate every 8 seconds with CSS opacity fade transition
- Dot navigation with 24px invisible hit targets and 6px visible dots via `::after` pseudo-elements
- Testimonials:
  - Stephen Francis, COO at Proximity VC
  - Tom Dunmore, VP Marketing at The Snow League
- Note: These are general character references. Build-specific testimonials to come.

### 2026-02-01 — Visual Design Refinement (Workshop Aesthetic)
**Plan:** `wild-cooking-pascal.md`

- Promoted oxide (#A65D3F) to structural accent color — CTA buttons, section dividers, portfolio card borders, hover states
- Increased paper noise opacity to 0.45
- Standardized letter-spacing to 2 values (0 and 0.1em)
- Replaced `transition: all` with specific property transitions
- Kept grid background — earned through workshop metaphor

### 2026-02-01 — Custom Site Details
- Added crosshair cursor (inline SVG data URI)
- Added oxide selection color (`::selection`)
- Redesigned form inputs to bottom-border-only (ruled lines)
- Added SR italic monogram to footer at 0.3 opacity
- Changed footer to "Built by me in The Sunshine State" with LinkedIn link

### 2026-02-01 — Slot Machine Lever (Ideas Modal)
- Built slot machine interaction for "What We'd Build" section
- Physical lever with pull animation (smooth drag + snap-back)
- 60 niche ideas that shuffle and land with staggered timing
- Three idea slots display simultaneously
- "Tap to pull" label

### 2026-02-01 — Portfolio Updates
- Swapped example niches on main page: Haul, LawnHQ, Pickleball State, JNXL Mailing Club
- Updated descriptions (Haul: "Estate sale growth marketing + newsletter")
- Removed audience size metrics from Pickleball State

### 2026-02-01 — Modal Close Button Fix
- Enlarged close button hit target with padding (12px vertical, 16px horizontal)
- Added `z-index: 10` so it sits above the lever
- Added `event.stopPropagation()` to prevent click from triggering the slot machine

### 2026-02-01 — Tab & Social Title
- Changed page title from "Your Build Partner — Sam Rahim" to "Sam Rahim — Build Partner"
- Updated OG and Twitter meta titles to match
- Leads with name since visitors are warm intros/referrals

### 2026-02-01 — Copy Iterations
- Hero headline: "The best ideas die in busy people's heads."
- Sub-headline: "Turn your industry knowledge or interests into a real product..."
- Bio line: "I quit startup life to build a portfolio of businesses with ambitious people."
- Softened How It Works step 4 language
- Removed "I'll reply if there's a fit" from form
- Added "or interests" to sub-headline
- Removed "Not a Fit" section entirely

### 2026-02-01 — Form Integration
- Google Apps Script integration (POST JSON, fire-and-forget with `mode: 'no-cors'`)
- Google Sheets as data store + email notification to sam@samrahim.com
- Success message with typewriter animation in bordered container
- Fire-and-forget pattern — shows success immediately without waiting for response

### 2026-02-01 — Infrastructure
- Git repo: `samrahim8/build` on GitHub
- Auto-deploys to Vercel
- Custom domain: `build.samrahim.com`
- OG image: SR monogram on parchment grid background
- Favicon: Inline SVG data URI with SR monogram
- Removed duplicate Vercel project (`build-partner`)

---

## Architecture

Single-file HTML site. All CSS and JS inline. No build tools, no frameworks, no dependencies beyond Google Fonts.

**File:** `index.html`
**Sections (in order):** Header > Hero > Who This Is For > The Studio > Testimonials > Portfolio > What We'd Build (+ slot machine modal) > How It Works > Work Together (form) > Footer
