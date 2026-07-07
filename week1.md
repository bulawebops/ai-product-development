# Module 1, Week 1 — Detailed Daily Outline
## HTML5 Semantics, Box Model, Flexbox, Grid, Responsive & Accessible Foundations

**Context:** First week of the program's Web track. Students arrive from the 360-hour core with dev-environment/Git/JS fundamentals already in place, but this is their first HTML/CSS in this track. No Tailwind yet (that's Week 2) — this week is plain HTML/CSS, deliberately, so students understand what Tailwind is abstracting before they start using it.

**Week deliverable:** A semantic, accessible, responsive static HTML/CSS skeleton of TaskFlow — a two-view layout (a dashboard/project-grid view and a single-project/task-list view), no styling framework, no JS interactivity yet. This becomes the literal starting point for Week 2.

---

## Day 1 (Monday) — HTML5 Semantics & Document Structure

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: semantic elements (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`) vs. generic `div`/`span`. Why semantics matter: SEO, accessibility (screen readers use landmarks), and maintainability for the next developer (you, in 3 weeks). |
| 1 | 45 min | **Guided demo**: instructor builds a simple semantic page live, narrating each choice ("why `<article>` here and not `<div>`?"). Students follow along. |
| 2 | 60 min | **Hands-on lab**: given a "div soup" HTML file (everything is `<div class="...">`), students refactor it into proper semantic HTML. Pushed to their own repo. |
| 3 | 45 min | **Applied**: students sketch and build the semantic skeleton for TaskFlow's dashboard view (header w/ nav, main w/ project cards as `<article>` elements, footer) — no styling yet, structure only. |
| 3 | 15 min | **Wrap-up**: quick pair-share — swap skeletons with a partner, check: does the HTML make sense read top-to-bottom with no CSS at all? |

**By end of day:** Students can look at a page and identify/justify semantic vs. non-semantic markup. TaskFlow dashboard skeleton exists as unstyled semantic HTML.

---

## Day 2 (Tuesday) — CSS Box Model & Flexbox

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: box model (content/padding/border/margin), `box-sizing: border-box` and why it's the practical default, margin collapse gotcha. |
| 1 | 45 min | **Direct instruction + demo**: Flexbox fundamentals — main axis vs. cross axis, `justify-content`, `align-items`, `flex-grow`/`flex-shrink`/`flex-basis`, `flex-wrap`. |
| 2 | 60 min | **Hands-on lab**: build a responsive nav bar (logo left, links right, collapsing behavior) using only Flexbox. |
| 3 | 45 min | **Applied**: style TaskFlow's header/nav from Day 1 using Flexbox. Lay out the project cards in a flex row (not yet Grid — that's tomorrow, so students feel the limitation and appreciate Grid more). |
| 3 | 15 min | **Wrap-up**: instructor names the specific pain point (cards wrapping awkwardly at odd widths) as a bridge into tomorrow's Grid lesson. |

**By end of day:** Nav bar and a flex-based card row are functional. Students have felt where Flexbox strains for 2D layout — sets up Day 3 motivation.

---

## Day 3 (Wednesday) — CSS Grid

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: Grid fundamentals — `grid-template-columns`/`rows`, `fr` units, `gap`, `grid-template-areas`, implicit vs. explicit grids. |
| 1 | 45 min | **Direct instruction**: Grid vs. Flexbox — when each is the right tool (Flexbox: 1D, content-driven; Grid: 2D, layout-driven), and how they combine (Grid for page layout, Flexbox inside individual grid cells). |
| 2 | 60 min | **Hands-on lab**: rebuild yesterday's card row as a responsive CSS Grid (`repeat(auto-fill, minmax(...))`) — same visual goal, better tool, students compare the two approaches directly. |
| 3 | 45 min | **Applied**: convert TaskFlow's dashboard project-card layout to Grid. Build the overall page layout (header / sidebar-nav / main content area) using `grid-template-areas`. |
| 3 | 15 min | **Wrap-up**: checklist review — does the layout hold up if you add 1 project card? 20? |

**By end of day:** TaskFlow dashboard has a real Grid-based page layout with a Flexbox-based card row nested inside — the combined pattern used in Weeks 2–4 build-outs.

---

## Day 4 (Thursday) — Responsive Design & Mobile-First

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: mobile-first methodology (base styles = smallest screen, media queries add complexity upward, not the reverse), `min-width` vs `max-width` queries, common breakpoint conventions, the viewport meta tag. |
| 1 | 45 min | **Direct instruction + demo**: responsive images (`srcset`, `sizes`, `object-fit`), fluid typography (`clamp()`), testing in dev tools' device toolbar and on an actual phone. |
| 2 | 60 min | **Hands-on lab**: take a fixed-width layout, refactor it mobile-first with 2 breakpoints (mobile / tablet / desktop). |
| 3 | 45 min | **Applied**: make TaskFlow's dashboard responsive — sidebar collapses to a hamburger/bottom-nav pattern on mobile, project grid drops from 3–4 columns to 1 column, nav bar from Day 2 adapts. |
| 3 | 15 min | **Wrap-up**: resize-the-browser demo — every student walks their layout from 320px to 1440px live, no broken states allowed. |

**By end of day:** TaskFlow dashboard is fully responsive across mobile/tablet/desktop. This is the layout that gets carried into Friday's accessibility pass and then Week 2's Tailwind conversion.

---

## Day 5 (Friday) — Accessibility

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: why accessibility isn't optional — legal (ADA/WCAG context), the "curb-cut effect" (a11y features that help everyone), how semantic HTML from Monday already buys most of this for free. |
| 1 | 45 min | **Direct instruction + live demo**: instructor navigates a real page using only a keyboard (Tab/Shift+Tab/Enter/Space) and a screen reader (VoiceOver/NVDA), narrating what's missing when it breaks. ARIA roles/labels — and the rule "no ARIA is better than bad ARIA." |
| 2 | 60 min | **Hands-on lab**: given a page with 5 seeded accessibility failures (missing alt text, unlabeled form input, non-focusable custom button, insufficient color contrast, illogical tab order), students find and fix each one using dev tools' accessibility inspector. |
| 3 | 45 min | **Applied — Week 1 checkpoint**: full accessibility audit of their own TaskFlow dashboard from Days 1–4 — keyboard nav test, screen reader pass, contrast check, focus-visible states on interactive elements. Fix everything found. |
| 3 | 15 min | **Wrap-up / demo**: 2–3 students volunteer to navigate their own TaskFlow dashboard live using only keyboard + screen reader in front of the class. |

**By end of week:** A semantic, responsive, keyboard-and-screen-reader-accessible static TaskFlow dashboard skeleton — the literal file that gets opened again in Week 2 to add Tailwind and component patterns on top.

---

## Notes for the Instructor

- **No Tailwind this week, on purpose.** Students should feel the manual work of writing box-model/flexbox/grid CSS by hand before Tailwind's utility classes make it faster — otherwise Tailwind looks like magic instead of a productivity tool built on concepts they already understand.
- **The Day 2→3 flex-to-grid friction is intentional**, not a pacing mistake — it's the fastest way to get students to *want* Grid instead of just being told to use it.
- **Friday's audit is the actual assessment for the week** — not a written quiz. If a student's dashboard fails the keyboard-nav or screen-reader test, that's the signal they need a review pass before Week 2, not a pass/fail gate that blocks them from moving on.
