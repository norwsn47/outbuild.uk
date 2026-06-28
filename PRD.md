# Outbuild — Product Requirements Document

> **Status:** Governing spec for the site rebuild (supersedes the current `index.html` implementation).
> **Last reconciled:** 2026-06-28 against the NEW DIRECTION design system + copy.
> **Note on provenance:** No prior PRD document existed in this repository. The "current PRD" referenced during reconciliation was the de-facto spec encoded in the existing `index.html` (an app-store-style card layout). Where this document and that implementation conflict, **this document governs.**

---

## 1. Summary

Outbuild is a small Edinburgh design collective that builds a growing set of small, single-purpose products. This site is its single-page home: a quiet, type-led editorial index that states a point of view ("less, better") and presents the work as a set. It is a place to **build and show ideas, not sell them.**

The design identity is carried entirely by type and space — no images, no photography, no decorative icons or glyphs. The one memorable element is the recurring naming lockup: **`[Product] by Outbuild`**.

## 2. Goals

- Present Outbuild's philosophy and its set of products on **one continuous-scroll page**.
- Make the **signature lockup** (`[Product] by Outbuild`) the thing the page is remembered by.
- Feel **crafted, intentional, and restrained** — the opposite of an "everything-tool."
- Meet non-negotiable quality floors: responsive to mobile, visible keyboard focus, `prefers-reduced-motion` respected.

## 3. Non-goals / Out of scope

- No e-commerce, sign-up, accounts, or selling. This is a showcase, not a storefront.
- No multi-page site, routing, or nav menu.
- No imagery, photography, illustration, decorative icons, or decorative glyphs.
- No CMS or backend. Static page.

## 4. Hard constraints (non-negotiable)

1. **Type is the design.** No images, no photography, no icons-as-decoration, no decorative glyphs. The words carry the page.
2. **One single page, one continuous scroll.** No routing, no nav menu.
3. **Responsive down to mobile.**
4. **Visible keyboard focus states** on every interactive element.
5. **Respect `prefers-reduced-motion: reduce`** — all motion disabled under it.

## 5. Design system

### 5.1 Palette

Near-monochrome on warm paper, with at most **one** very quiet accent. No terracotta/orange accent (cliché). Values may be adjusted to taste but must stay in this register:

| Token | Suggested value | Use |
|---|---|---|
| `--paper` | `#F1ECE3` | warm off-white background (never pure white) |
| `--ink` | `#1B1A17` | near-black primary text |
| `--muted` | `#8C867A` | secondary text, the "by Outbuild" treatment, labels |
| `--hair` | `#D8D1C4` | hairline rules / dividers |
| `--accent` | quiet deep green (TBD hex) | **link hover/focus only** — muted, desaturated, almost unnoticeable. At most one accent on the page. |

### 5.2 Typography

- **One** confident grotesque / neo-grotesque typeface across the whole page, at multiple weights. Single-family discipline is the point. Candidate (Google Fonts): Archivo, Hanken Grotesk, Inter Tight, or Schibsted Grotesk — **pick one** (see Open Questions).
- Do **not** pair a fashionable serif display on cream (default AI look — explicitly unwanted).
- Large display type: **tight tracking, tight line-height.**
- Body: **normal tracking, comfortable line-height.**
- Small **uppercase labels** (letter-spaced, `--muted`, ~0.75rem) act as quiet section signposts. These are the only structural decoration.
- **No numbered markers** (no 01 / 02 / 03). The work is a set, not a sequence.
- **Exception — the wordmarks/lockups** (the four product names, the `by Outbuild` sign-off, and the header wordmark) do **not** use the page typeface. They follow the products' own `Logo` component so the brand reads identically here and on each live product. See §5.4.

### 5.2.1 Wordmark spec (matches the products' `Logo` component)

The naming lockup is a brand asset, not page typography. It uses the native **system font stack** and fixed proportions derived from a base size (the products render it at `size=40`; here the product name is set at the page's display scale and everything else scales from it):

| Part | Rule |
|---|---|
| Font family | `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif` |
| Product name | weight **700**, colour **`#1c1c1c`**, letter-spacing **-0.01em** |
| ` by Outbuild` | font-size **0.6×** the name (the `0.36 / 0.6` ratio), weight **400**, colour **`#888888`** |
| Layout | inline, **baseline-aligned**, gap **0.3em at the "by" size** (≈ `0.18em` of the name), line-height ~1 |

All sizes scale proportionally with the product-name size. The header `Outbuild` wordmark uses the same system font, kept small at medium weight. On linked tiles the hover/focus affordance still applies (see §5.4) — `by Outbuild` shifts `#888888` → `--accent`.

### 5.3 Layout & mood

Generous negative space, a clear grid, content held to a readable measure. Crafted and intentional, not flashy. When in doubt, remove something.

### 5.4 The signature lockup (the one memorable element)

```
[Product]  by Outbuild
```

- `[Product]` — solid/bold weight, `--ink`.
- `by Outbuild` — lighter weight, `--muted`.
- This lockup is the site's wordmark and appears on **every** work item. (For its exact type treatment, see §5.2.1.)
- **Clickable affordance** (override): each work tile now shows its **product URL with a small `→` arrow** as the explicit click cue. On hover/focus the URL + arrow shift `--muted` → `--accent` (the lockup itself stays put). **Disable the transition under `prefers-reduced-motion`.** _(This supersedes the earlier "no arrow / colour-shift the by-line" affordance.)_

## 6. Page structure & content (top to bottom)

Order (top to bottom): **Header → Purpose → Philosophy → The work → About.** (The standalone Why now and Vision sections were removed; see §6.4.) Copy below is **verbatim** apart from the hyphen convention noted above. Hierarchy: Purpose is the giant hero; Philosophy is smaller beneath it; The Work is the centrepiece; everything else is quiet.

### 6.1 Header — the name
Small wordmark, top-left: **`Outbuild`** (just the word, medium weight — a quiet signature, not a big masthead). No tagline.

> **Punctuation convention (override):** the page uses a plain hyphen `-` in place of em dashes throughout the copy below. The copy is otherwise unchanged.

### 6.2 Purpose — main hero (largest type on the page)
> Most products do too much. We do less, better - human-centered design, stripped back to what matters.

Set big and confident; the visual anchor of the whole page. May break across lines for rhythm, with the "- human-centered design, stripped back to what matters" clause stepped down in size or weight.

### 6.3 Philosophy
Label: **`PHILOSOPHY`**
> We don't start with the product. We start with the problem. Then we take away everything that isn't the answer.

### 6.4 The work — the centrepiece
Label: **`THE WORK`**

> **Override:** the standalone **Why now** and **Vision** sections are removed. The Why now line is merged into the work intro below.

Intro (Why now folded in):
> Everything's becoming an everything-tool. We'd rather build one thing that does one thing - properly. A growing set of small, simple products - each one solving a single real problem.

Four tiles. Each tile is a **link to that product's live site** and contains, in order:
1. the signature lockup - `[Product Name] by Outbuild`
2. the **situation line** (the pain point - set apart, quiet/observational)
3. the **one-line description** of what it does
4. the **product URL with a small `→` arrow** - the explicit, clearly-clickable affordance (this overrides the earlier "no arrow" rule)

Keep product **features off** these tiles - only the situation line, the one do-this line, and the URL. No sub-event chips, no category groupings, no numbered markers.

**Tile layout:** a clean vertical stack separated by hairline rules in `--hair` - an editorial "index of work" feel. No cards with heavy borders or shadows; space and hairlines do the structuring.

**The four tiles (verbatim):**

**Race Spectator Planner - by Outbuild**
- Situation: Two friends, two paces, one race - and no obvious place to stand to catch them both.
- Does: Import a GPX route, add the runners, and see where each one will be, and when.
- Link: `https://racespectator.outbuild.uk` (shown as `racespectator.outbuild.uk →`)

**Munro Tracker - by Outbuild**
- Situation: Trip planning scattered across Walkhighlands, the bothy maps and a dozen tabs.
- Does: Pulls the Munro and bothy resources into one place to plan the next route from Edinburgh.
- Link: `https://munro.outbuild.uk` (shown as `munro.outbuild.uk →`)

**Explore - by Outbuild**
- Situation: Every "best local spots" list on holiday is the same AI slop.
- Does: A shareable map of real recommendations, in a host's own voice.
- Link: `https://explore.outbuild.uk` (shown as `explore.outbuild.uk →`)

**Scorecard - by Outbuild**
- Situation: A golf round scribbled on a crumpled card, lost before the car park.
- Does: A clean digital golf scorecard - record the round, keep it, look back on it.
- Link: `https://scorecard.outbuild.uk` (shown as `scorecard.outbuild.uk →`) — now live; no longer "coming soon".

### 6.7 About — the footer beat
Label: **`ABOUT`**
> Outbuild is a small Edinburgh design collective. It comes from one person's love of the outdoors and active life - so that's where the building starts: the planning, the remembering, and the sharing around the things people do outside. For now this is a place to build and show ideas, not sell them.

Contact line (included): `williamadamgriffiths@gmail.com`

---

### 6.8 PLACEHOLDER — owner's vision / positioning content
> **To be supplied by the owner.** This section is intentionally left empty. The site owner will add their own vision / positioning content to the PRD here. Do not invent or draft this content.

---

## 7. Motion

- A gentle **staggered fade/rise on the Purpose lines** at page load.
- The quiet **hover/focus affordance on work items** (the URL + `→` arrow shift to `--accent`; no movement of the lockup itself).
- **Nothing else.** Extra animation undercuts the restraint.
- **All motion disabled under `prefers-reduced-motion: reduce`.**

## 8. Accessibility (quality floors)

- Visible keyboard focus on every interactive element.
- `prefers-reduced-motion: reduce` disables all motion, including hover transitions.
- Responsive down to mobile; content held to a readable measure at all widths.
- Sufficient contrast for `--ink` on `--paper`; `--muted` used only for secondary text and never as the sole carrier of essential meaning.
- All four work tiles are live links; the visible URL doubles as the click cue. (If a future product isn't live, render its tile as non-clickable and convey that state to assistive tech.)

## 9. Technical notes

- Static single page. No backend, no routing.
- Single grotesque typeface loaded from Google Fonts (chosen family TBD).
- Lockup hover/focus and Purpose load animation gated behind the reduced-motion media query.

---

## Appendix A — Items carried over from the current implementation that are NOT in the new direction

These exist in the current `index.html` and are **not** referenced by the new direction. Decisions needed (see Open Questions); none are assumed to survive unless confirmed:

- **`build-with-claude.html` "Building with Claude" guide page + the "Notes" section** linking to it. Conflicts with the single-page / no-routing constraint.
- **Marathon Pacer** as a standalone product (appears folded into / replaced by Race Spectator Planner).
- **Generic "Race Spectator" + event-specific versions** (London, Prague) and their subdomains.
- **Existing live subdomains** (`munro.`, `explore.`, `pacer.`, `racespectator.outbuild.uk`) — candidate live URLs for the TODO links.
- **Tagline "Tools for people who move"** and the `meta description` of the same.
- **Contact email** in the hero blurb (now an optional TODO in About).
- **Copyright/footer line** "© 2026 Outbuild".
