# Ninjai
## The home hub, reimagined.

**Live site:** ninjai.pascalmarsh.com
**Vercel URL:** ninjai-eta.vercel.app
**GitHub:** github.com/pascalmarsh/ninjai

---

## Current Setup (March 2026)

| Service | Role | URL |
|---------|------|-----|
| GitHub | Source files + version control | github.com/pascalmarsh/ninjai |
| Vercel | Hosting + auto-deploy | vercel.com / pascalmarsh-7622 |
| Squarespace | Domain DNS only | account.squarespace.com |
| Claude | Build partner | claude.ai |

**Deploy pipeline:** Push/upload to GitHub → Vercel detects change → auto-deploys in ~20 seconds

**DNS:** pascalmarsh.com managed by Squarespace. Custom record:
- Host: `ninjai`
- Type: CNAME
- Value: `c8677b3bb53a0c3f.vercel-dns-017.com`

---

## File Structure

```
ninjai/
├── index.html              ← Main campaign site
├── ninjai-film.html        ← Animated product film placeholder
├── ninjai-woofer.html      ← Woofer product detail + acoustic engineering
├── README.md               ← This file
└── images/
    ├── ninjai-hero.jpeg        Marketing render (white bg)
    ├── ninjai-real.jpeg        Klein Blue finished product
    ├── ninjai-detail.jpeg      Top-down origami detail
    ├── ninjai-glow-1.jpeg      Dramatic warm glow (video poster)
    ├── ninjai-glow-2.jpeg      Warm glow — carousel slide 2
    ├── ninjai-room-1.jpeg      Bedroom nightstand context
    ├── ninjai-room-2.jpeg      Room context lit
    ├── ninjai-room-3.jpeg      Room context — carousel hero
    ├── ninjai-room-wide.jpeg   Wide room shot
    ├── ninjai-table-lit.jpeg   On side table, shade close-up
    ├── ninjai-proto-base-1.jpeg First shade prototype (tilted)
    ├── ninjai-base-bare-1.jpeg  Bare base — no shade
    └── ninjai-base-bare-2.jpeg  Bare base form study
```

---

## Pages

### index.html — Main site
Full campaign page with:
- Animated MarshMade logo (brand bar)
- 16:9 Ken Burns hero carousel (4 slides)
- Animated product film placeholder with poster
- Dark cinematic philosophy section
- 4-model comparison grid
- Feature bento grid
- Light / 10,000 lux section with animated counter
- Accessories section
- Philosophy / Noguchi section
- Open source platform pills
- History timeline (10 events, alternating left/right)
- Final CTA

### ninjai-woofer.html — Woofer detail page
Linked from the Woofer "Learn more →" button. Contains:
- Dark cinematic hero with stats
- Ceramic acoustic engineering story
- Full technical cross-section drawings (front + side elevation, 1:5 scale)
- Passive radiator explainer
- Full spec grid (12 cells)
- Order CTA

### ninjai-film.html — Animated film placeholder
8-scene cinematic animation using Canvas + CSS. Plays in the video section when the poster is clicked. Replace with a real .mp4 when available.

---

## How to Update

### Deploy any change
1. Go to github.com/pascalmarsh/ninjai
2. Click the file → Edit (pencil) or use Upload
3. Commit → Vercel deploys automatically

### Swap a carousel image
Find `<!-- HERO CAROUSEL -->` in index.html. Update `src="images/filename.jpeg"` in any slide div. Upload the new photo to the `images/` folder first.

### Replace the film placeholder with a real video
In index.html, find `<!-- VIDEO / FILM SECTION -->`. Replace the poster/iframe block with:
```html
<video src="images/ninjai-film.mp4"
  poster="images/ninjai-glow-1.jpeg"
  controls playsinline
  style="width:100%;display:block;aspect-ratio:16/9;">
</video>
```
Upload the .mp4 to images/ first.

### Add a new timeline event
Find `<!-- HISTORY TIMELINE -->` in index.html. Copy an existing `tl-event` block. Alternate left/right placement. Update image src, title, body text, and date.

### Update pricing
Search for: `€299` `€499` `€699` `€999`

### Update model specs
Search for the model name comment e.g. `<!-- Ninjai Woofer -->`. Edit the `<li>` items.

### Add new photos
1. Name: lowercase with hyphens e.g. `ninjai-kitchen-2026.jpeg`
2. Upload to `images/` folder on GitHub
3. Reference as `src="images/ninjai-kitchen-2026.jpeg"`
4. Compress at tinypng.com if over 500KB

---

## Logo Animation

The MarshMade logo (orange + blue squares) animates in the brand bar.

**Behaviour:**
- Page load: single spin after 800ms, then static
- Scroll: loops while scrolling, decelerates when you pause
- Hover over logo or any image: loops, decelerates on leave
- BPM drifts naturally between 120–140 while looping

**To change logo colours:** Search for `#F5A623` (orange) and `#1B2FC2` (blue) in index.html.

**To change logo size:** Find `width: 40px; height: 44px` in the brand-logo-wrap CSS.

---

## Pages Still To Build

| Page | Status | Notes |
|------|--------|-------|
| ninjai-woofer.html | ✅ Live | Full acoustic engineering detail |
| ninjai-plus.html | ⬜ Planned | Ninjai + detail page |
| ninjai-cinema.html | ⬜ Planned | Cinema detail page |
| shop.html | ⬜ Planned | Interactive configurator + basket |
| ninjai-accessories.html | ⬜ Planned | Accessories detail + upsell |

---

## Moving to Next.js (when ready for Claude agent integration)

1. `npx create-next-app@latest ninjai --typescript`
2. Move HTML content into `app/page.tsx`
3. Add API routes in `app/api/` for Claude integration
4. Add `ANTHROPIC_API_KEY` to Vercel environment variables
5. Connect same GitHub repo to Vercel — existing deploys continue

---

## Accounts

| Service | Login |
|---------|-------|
| GitHub | pascalmarsh |
| Vercel | pascalmarsh-7622 (GitHub login) |
| Squarespace | pascal.marsh@gmail.com |

*Last updated: March 2026*
