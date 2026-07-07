# Rollback Status

## The Trilogy (Internal Name — not visible on site)

| Part | Name | Content |
|------|------|---------|
| I | **HOME** | Title card — CODE IS POETRY → Volume 1 |
| II | **BRIEF** | Investor slides 0–7 + slide 08 (WORK) |
| III | **WORK** | Minimal ENTER page with stats |
| IV | **SHOWREEL** | 70 cards across 7 collections (4 real images, 3 gradients) |

---

## File: combined.html

### Current Changes from Originals

| Change | Original | Current |
|--------|----------|---------|
| Combined file created | Two separate files | `combined.html` merges title-card + investor-brief + WORK + SHOWREEL |
| `.deck` dimensions | `height:100%; width:100%` | `height:100vh; width:100%` |
| Title card skip | No skip | Click anywhere on title card to skip |
| Script architecture | Nested timeouts with shared `current` var | Generation-based timeout invalidation, clean functions |
| www.empathystudio.in link | Light color | Dark color (`var(--ink)`), no underline |
| Slide 07 NEXT → | Stays on last slide | Advances to slide 08 (WORK) |
| Slide 08 (WORK) | None | New slide: EMPATHY Studio heading, stats (47/12/3/8), ENTER link |
| Trilogy nav | None | HOME · BRIEF · WORK · SHOWREEL — top-left, always visible |
| Trilogy nav scroll-hide | None | Hides on scroll down, shows on scroll up (showreel phase) |
| SHOWREEL section | None | 70 cards, 7 collections, GSAP + ScrollTrigger + Lenis |
| Showreel footer | None | Centered footer matching WORK.html style |
| Brief slide 7 footer | Heart emoji `❤` | HTML entity `&#10084;`, phone numbers reordered |
| Collection nav | None | Left-side vertical nav (hair · look-book · cafe · yoga · restaurant · occult · film) |
| Card hover light | None | Light-passing effect via GSAP on hover |
| Card stagger reveal | None | Cards animate in on scroll via ScrollTrigger |
| Collection tagline parallax | None | Taglines shift -20px on scroll |

### Image Status

| Collection | Images | Source |
|------------|--------|--------|
| Hair | 10 real `<img>` | `../PRESENTATION/images/hair/` |
| Look-Book | 10 real `<img>` | `../PRESENTATION/images/lookbook/` |
| Cafe | 10 real `<img>` | `../PRESENTATION/images/cafe/` |
| Film | 10 real `<img>` | `../PRESENTATION/images/film/` |
| Yoga | 10 CSS gradients | No source images |
| Restaurant | 10 CSS gradients | No source images |
| Occult | 10 CSS gradients | No source images |

### Known Issues

- [ ] Title card restart from brief may still show blank (needs testing after script rewrite)
- [ ] 3 collections (Yoga, Restaurant, Occult) have no real images — using placeholder gradients
- [ ] Yoga, Occult, and some Restaurant cards link to `#` (no live Vercel deploy)

### Rollback Steps

1. Restore original `title-card.html` and `empathy-studio-investor-brief.html`
2. Delete `combined.html`

---

## File: WORK.html

### Changes

| Change | Original | Current |
|--------|----------|---------|
| Trilogy nav | None | HOME · BRIEF · WORK · SHOWREEL (4 links, top-left) |
| BRIEF link | `index.html#brief` | `combined.html` (loads combined file) |

### Rollback Steps

1. Remove `.trilogy-nav-work` CSS
2. Remove Trilogy nav HTML
3. Restore original nav content

---

## File: PRESENTATION/index.html

### Changes

| Change | Original | Current |
|--------|----------|---------|
| Trilogy nav added | No nav | HOME · BRIEF · WORK in sticky nav (desktop + mobile) |
| Back button | None | Replaced with full Trilogy nav |

### Rollback Steps

1. Remove `.trilogy-nav-work` CSS
2. Remove Trilogy nav HTML from nav-inner and nav-mobile
3. Restore original nav-inner content
