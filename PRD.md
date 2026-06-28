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

### 5.3 Layout & mood

Generous negative space, a clear grid, content held to a readable measure. Crafted and intentional, not flashy. When in doubt, remove something.

### 5.4 The signature lockup (the one memorable element)

```
[Product]  by Outbuild
```

- `[Product]` — solid/bold weight, `--ink`.
- `by Outbuild` — lighter weight, `--muted`.
- This lockup is the site's wordmark and appears on **every** work item.
- **Hover/focus affordance** (linked work items only): quiet, **no arrow**, no movement of the lockup itself. Choose **one**: `by Outbuild` shifts `--muted` → `--accent`, **or** a thin underline appears under the product name. Keep it subtle; **disable the transition under `prefers-reduced-motion`.**

## 6. Page structure & content (top to bottom)

Copy below is **verbatim** and must not be rewritten, expanded, or paraphrased. Hierarchy: Purpose is the giant hero; Philosophy is smaller beneath it; The Work is the centrepiece; everything else is quiet.

### 6.1 Header — the name
Small wordmark, top-left: **`Outbuild`** (just the word, medium weight — a quiet signature, not a big masthead). No tagline.

### 6.2 Purpose — main hero (largest type on the page)
> Most products do too much. We do less, better — human-centered design, stripped back to what matters.

Set big and confident; the visual anchor of the whole page. May break across lines for rhythm, with the "— human-centered design, stripped back to what matters" clause stepped down in size or weight.

### 6.3 Philosophy
Label: **`PHILOSOPHY`**
> We don't start with the product. We start with the problem. Then we take away everything that isn't the answer.

### 6.4 Why now
Label: **`WHY NOW`**
> Everything's becoming an everything-tool. We'd rather build one thing that does one thing — properly.

### 6.5 The work — the centrepiece
Label: **`THE WORK`**
Intro line:
> A growing set of small, simple products — each one solving a single real problem.

Four tiles. Each tile is a **link to that product's live site** and contains, in order:
1. the signature lockup — `[Product Name] by Outbuild`
2. the **situation line** (the pain point — set apart, quiet/observational)
3. the **one-line description** of what it does

Keep product **features off** these tiles — only the situation line and the one do-this line. No sub-event chips, no category groupings (e.g. no "Running" divider), no numbered markers.

**Tile layout:** a clean vertical stack (or simple grid) separated by hairline rules in `--hair` — an editorial "index of work" feel. No cards with heavy borders or shadows; space and hairlines do the structuring.

**The four tiles (verbatim):**

**Race Spectator Planner — by Outbuild**
- Situation: Two friends, two paces, one race — and no obvious place to stand to catch them both.
- Does: Import a GPX route, add the runners, and see where each one will be, and when.
- Link: _TODO — live URL, or mark "coming soon" and render as non-clickable._

**Munro Tracker — by Outbuild**
- Situation: Trip planning scattered across Walkhighlands, the bothy maps and a dozen tabs.
- Does: Pulls the Munro and bothy resources into one place to plan the next route from Edinburgh.
- Link: _TODO — live URL, or mark "coming soon"._

**Explore — by Outbuild**
- Situation: Every "best local spots" list on holiday is the same AI slop.
- Does: A shareable map of real recommendations, in a host's own voice.
- Link: _TODO — live URL, or mark "coming soon"._

**Scorecard — by Outbuild**
- Situation: A golf round scribbled on a crumpled card, lost before the car park.
- Does: A clean digital golf scorecard — record the round, keep it, look back on it.
- Link: _TODO — live URL, or mark "coming soon"._

### 6.6 Vision
Label: **`VISION`**
> A world with fewer features and more clarity — where the small things are done right.

### 6.7 About — the footer beat
Label: **`ABOUT`**
> Outbuild is a small Edinburgh design collective. It comes from one person's love of the outdoors and active life — so that's where the building starts: the planning, the remembering, and the sharing around the things people do outside. For now this is a place to build and show ideas, not sell them.

_TODO (optional): a single contact line here if wanted — e.g. an email or one social link. Leave out entirely if the page is meant to be a closed shop, just the work._

---

### 6.8 PLACEHOLDER — owner's vision / positioning content
> **To be supplied by the owner.** This section is intentionally left empty. The site owner will add their own vision / positioning content to the PRD here. Do not invent or draft this content.

---

## 7. Motion

- A gentle **staggered fade/rise on the Purpose lines** at page load.
- The quiet **hover/focus affordance on work items** (colour shift or underline — no arrow, no movement of the lockup itself).
- **Nothing else.** Extra animation undercuts the restraint.
- **All motion disabled under `prefers-reduced-motion: reduce`.**

## 8. Accessibility (quality floors)

- Visible keyboard focus on every interactive element.
- `prefers-reduced-motion: reduce` disables all motion, including hover transitions.
- Responsive down to mobile; content held to a readable measure at all widths.
- Sufficient contrast for `--ink` on `--paper`; `--muted` used only for secondary text and never as the sole carrier of essential meaning.
- "Coming soon" tiles render as non-clickable (not a dead link); convey state to assistive tech.

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
