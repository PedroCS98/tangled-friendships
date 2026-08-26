# Tangled Friendships — Future Ideas

Unscheduled ideas. Not Phase II, not committed to Phase III.
Revisit when the coursework is delivered and the client relationship moves to maintenance.

---

## Client-editable product data

**Problem:** the clients add and sell bracelets constantly. Right now every change means editing HTML.

**Idea:** move product data out of `products.html` into a data file. The page renders the grid from that file, so adding or removing a bracelet is a data edit, not a code edit.

```json
{
  "id": "slash-6-purple-yellow",
  "type": "Slash",
  "group": "patterns",
  "threads": 6,
  "price": 3.00,
  "colours": ["yellow-purple"],
  "image": "slash-6-purple-yellow.jpg",
  "inStock": true
}
```

**Notes:**
- Card size is derived from `group`, not stored per product — Patterns render wide, Signature renders large, everything else small.
- With `grid-auto-flow: dense` the grid packs itself, so product order in the file doesn't matter. No manual spacing rules for the clients to follow.
- Requires JS (`fetch`), so it lands in Phase III or later. At that point `products.html` becomes a template and the hand-written 29 cards go away.
- Images still have to be added to `assets/` with matching filenames — that is the harder half of the job and the data file does not solve it.

**Open question — is JSON the right format for them?**

Both owners answered *"prefiro que alguém tome conta disso por mim"* on the intake form, so self-service may not be what they actually want. Options in rough order of how much they'd have to learn:

| Option | Client effort | Build effort | Risk |
|---|---|---|---|
| Pedro edits on request | none | ongoing | bottleneck on Pedro |
| Google Sheet → published as JSON | low, familiar | medium | sheet structure can drift |
| CSV in the repo | medium | low | still Git |
| Raw JSON in the repo | high | low | one missing comma breaks the page |
| Headless CMS | low | high | cost, another account |

A Google Sheet is probably the sweet spot: they already know spreadsheets, it validates nothing but fails visibly, and it needs no Git.

---

## Collections page

Themed sets — shared palette, season, or concept. Distinct from Products, which is the full catalogue.
Blocked on the clients defining what a collection actually is.

## Product detail pages

One page per product. Larger photos, full thread breakdown, size guide, add to cart.
Needed before the cart does anything real.

## Testimonials

Both owners requested it on the form. Works as a strip on `index` or `about` — does not need its own page.
Blocked on them supplying actual testimonials.

## Bundles

Bracelets sold together at a set price. Already a filter pill on the Products page with nothing behind it.

## Favourites

`fa-regular fa-heart` / `fa-solid fa-heart` toggle on product cards. Needs storage to persist.

## Search

`fa-solid fa-magnifying-glass`. Low value while the catalogue is small and well filtered.

## Gallery lightbox

Click a mosaic photo to open it full size. Achievable with `:target` and no JS.

## Stitch motif

Section dividers as a running-stitch line via `repeating-linear-gradient`, nav active state as a stitched underline.
Brand-specific, cheap in CSS, no template does it.

## Kumihimo and obijime

Previously sold, clients want to bring them back. The techniques page is still built around them.
Blocked on client confirmation.

## Custom order page

Was `builder.html` in the original plan, dropped from Phase II. Bespoke commissions, distinct from the stock model on Products.

---

*Anything here that gets scheduled moves to the README under the relevant phase.*
