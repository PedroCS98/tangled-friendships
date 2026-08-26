# Tangled Friendships — Website Project

> Handmade bracelets and accessories — *Where knots become bonds.*

GitHub: https://github.com/PedroCS98/tangled-friendships

---

## Phase I — HTML Foundation ✅ Complete

Single-page semantic HTML — header, hero, about, techniques (video + pricing table), collections, FAQ, contact form, footer.

---

## Phase II — Multi-Page Site + CSS Design System ✅ Complete

**Branch:** `PhaseII/multipage-css`

### File Structure

```
tangled-friendships/
├── index.html
├── pages/
│   ├── about.html
│   ├── techniques.html
│   ├── products.html
│   ├── gallery.html
│   ├── contact.html
│   ├── account.html
│   └── cart.html
├── css/
│   ├── style.css        ← shared: root, reset, header, hero, featured, FAQ, footer
│   ├── about.css
│   ├── techniques.css
│   ├── products.css     ← also loaded by index.html for the featured cards
│   ├── gallery.css
│   ├── contact.css
│   ├── account.css
│   ├── cart.css
│   └── thread-dots.css  ← 27 thread colour classes
└── assets/
    ├── gallery/
    ├── products/
    └── misc/            ← logo variants, suns
```

### Design System

| Token | Value |
|---|---|
| `--color-primary` | `#7B3FAE` (purple) |
| `--color-accent` | `#F5C842` (yellow) |
| `--color-bg` | `#FEF8D5` (warm light yellow) |
| `--color-text` | `#1A0033` (near-black purple) |
| `--color-surface` | `#FAF7FF` (pale lilac, cards) |
| `--font-heading` | Caveat |
| `--font-body` | DM Sans |

Spacing tokens `--size-xs` through `--size-xl` (0.5rem → 3rem).
Icons: Font Awesome 7 via CDN. Breakpoints: 768px (tablet), 480px (phone).

### Steps

- [x] Step 1 — Git setup
- [x] Step 2 — Page shells
- [x] Step 3 — Navigation linking
- [x] Step 4 — CSS design system
- [x] Step 5 — Header and footer components (burger menu)
- [x] Step 6 — Page layouts and content
- [x] Step 7 — Responsiveness and accessibility
- [x] Step 8 — Animations and polish
- [ ] Step 9 — PR and submission

### Product model

Stock items, not configurable products — each physical bracelet is its own entry.
29 products across 4 groups. Card size is a property of the group, so filtering never breaks the grid.

| Group | Types | Card |
|---|---|---|
| Basics | Lead, Thin, Weave, Trail, Zipper, Twist, DNA, Anchor, Coil | 1×1 |
| Patterns | Slash, Arrow, Flip Flop, Ocean | 2×1 |
| Shapes | Bloom | 1×1 |
| Signature | Tangled Friendships | 2×2 |

Pricing: 6 threads €2.20, +€0.20 per extra thread. Thin is 4-thread only, Coil 6-thread only.
Products grid uses `grid-auto-flow: dense` — 29 items pack to 13 rows at 3 columns with no interior gaps.

**Thread dots** — one dot per colour in the piece, not per thread. Solid threads are flat colours,
multicolour threads are `conic-gradient` thirds. 27 classes in `thread-dots.css`.

---

## Notes

- All copy is provisional and written in-house — needs client sign-off before go-live.
- `.mp4` video is a placeholder credited to ROANOKE — replace before going live.
- Technique page images are web placeholders — replace with client photography.
- Filter pills and the colour toggle are visual only — wiring is Phase III.

---

## Phase III — JavaScript

- Filter pill logic, including the "only these colours" toggle
- Thread count slider (index-based, 5 positions → 4/6/9/12/14)
- Cart functionality
- Product detail pages
- Portuguese translation under `/pt/`

See `FUTURE-IDEAS.md` for unscheduled work.