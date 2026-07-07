# Module 1, Week 2 — Detailed Daily Outline
## Tailwind CSS, Design Systems, Component Patterns, No-AI Checkpoint

**Context:** Students arrive with a semantic, responsive, accessible static TaskFlow dashboard skeleton built entirely in hand-written CSS (Week 1). This week, the same skeleton gets restyled in Tailwind — the point isn't new visual design, it's recognizing that Tailwind's utilities are the box-model/flexbox/grid concepts from last week, expressed faster.

**Week deliverable:** The Week 1 TaskFlow dashboard, fully restyled with Tailwind, using a consistent design system (spacing/type/color scale) and reusable component patterns (card, nav, form styles) — still no JS, still no framework. This is the file Module 2 opens to start the React rebuild.

---

## Day 1 (Monday) — Tailwind Setup & Utility-First Workflow

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: what utility-first CSS is and the actual argument for it — no more naming things ("is this `.card` or `.card-item`?"), styles colocated with markup, no dead CSS accumulating over a project's life. Install and configure Tailwind in a project. |
| 1 | 45 min | **Guided demo**: instructor takes a chunk of Monday-Week-1-style hand-written CSS (e.g., the flex nav bar) and converts it to Tailwind utilities live, narrating the 1:1 mapping (`display:flex` → `flex`, `justify-content:space-between` → `justify-between`). |
| 2 | 60 min | **Hands-on lab**: students convert their own Week 1 nav bar and card row to Tailwind utility classes, no custom CSS allowed. |
| 3 | 45 min | **Applied**: convert the full TaskFlow dashboard's structural layout (Grid page layout, Flexbox card row) from Week 1 to Tailwind. |
| 3 | 15 min | **Wrap-up**: quick discussion — where did Tailwind feel faster? Where did it feel more verbose than plain CSS? |

**By end of day:** TaskFlow dashboard's layout is fully converted to Tailwind utilities, visually identical to Friday's Week 1 version.

---

## Day 2 (Tuesday) — Design Systems: Spacing, Typography, Color

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: why arbitrary values (`mt-[13px]`) are a smell — Tailwind's default spacing/type scale exists so a whole app stays visually consistent without anyone deciding pixel values ad hoc. Customizing `tailwind.config.js` (theme extension, custom colors, custom spacing if truly needed). |
| 1 | 30 min | **Legacy-recognition comparison**: side-by-side — the same button styled in Sass (with a mixin), Bootstrap (with utility/component classes), and Tailwind. Not a build exercise — just enough that students aren't lost if they land on a legacy codebase using either. |
| 2 | 60 min | **Hands-on lab**: define a small design system in `tailwind.config.js` for TaskFlow — brand colors, a type scale (heading sizes, body, caption), consistent spacing rhythm — then audit the dashboard for any inconsistent one-off values and fix them to use the scale. |
| 3 | 45 min | **Applied**: apply the design system to typography across the whole dashboard (headings, card titles, body text, labels) — everything pulls from the same scale, nothing arbitrary. |
| 3 | 15 min | **Wrap-up**: peer review — swap dashboards, check: does every text size/color trace back to the config, or is there a stray `text-[15px]` hiding somewhere? |

**By end of day:** TaskFlow has a defined, consistent design system (colors, type scale, spacing) driving all of its styling — not just "it looks fine."

---

## Day 3 (Wednesday) — Component Patterns

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: recognizing a component before you have components — a "card" isn't yet a React component (that's Module 2), but it should already be a repeatable, consistent utility pattern. When `@apply` is worth it (rare, for a truly repeated cluster) vs. just repeating utilities (usually fine, and clearer to read). |
| 1 | 45 min | **Guided demo**: instructor builds the canonical TaskFlow "project card" pattern once — spacing, border, shadow, hover state — as a documented, reusable utility cluster. |
| 2 | 60 min | **Hands-on lab**: students build 3 component patterns for TaskFlow — project card, nav link (with active state), and a form input — each one consistent and reused everywhere it appears, not re-invented per instance. |
| 3 | 45 min | **Applied**: apply these three patterns across the entire dashboard, replacing any one-off styled elements from Days 1–2 with the standardized patterns. |
| 3 | 15 min | **Wrap-up**: instructor spot-checks 2–3 dashboards for consistency — every card should look and behave identically. |

**By end of day:** Three documented, reused component patterns (card, nav link, form input) applied consistently across the whole TaskFlow dashboard.

---

## Day 4 (Thursday) — No-AI Checkpoint: Nav + Card Layout

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **No-AI checkpoint (timed, 45 min)**: from a written spec (not a screenshot), students build a new nav + card layout — different content than TaskFlow, to prevent copy-paste from muscle memory — using only Tailwind, no AI assistant of any kind. |
| 1 | 45 min | **AI-assisted round**: same spec, fresh file, students now use an AI coding assistant to scaffold the same layout. |
| 2 | 60 min | **Structured critique**: students compare their own two versions side by side — Where did the AI version diverge from the design-system rules established Tuesday/Wednesday (arbitrary values, inconsistent spacing, patterns that don't match the established card/nav components)? Where was AI faster with no quality cost? Write a short critique (5–6 sentences) on when they'd reach for AI here and when they wouldn't. |
| 3 | 45 min | **Applied**: apply anything useful from the AI-assisted round back into the actual TaskFlow dashboard, but only after manually verifying it matches the design system — no unreviewed AI output ships. |
| 3 | 15 min | **Wrap-up**: 2–3 students share one thing the AI got subtly wrong that would've been easy to miss. |

**By end of day:** Every student has direct, felt evidence of where AI-generated Tailwind drifts from an established design system — the point of this checkpoint isn't "AI is bad," it's "AI output still needs a human who knows the rules to check it."

---

## Day 5 (Friday) — Forms, Polish & Week Checkpoint

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: form styling patterns in Tailwind — inputs, labels, validation states (error/success), focus rings (tying back to Week 1's accessibility work — focus states can't be lost when restyling). |
| 1 | 45 min | **Hands-on lab**: build TaskFlow's "new task" form using the form input pattern from Wednesday, with proper labels, focus states, and error-state styling. |
| 2 | 60 min | **Applied — full dashboard polish**: pull everything from the week together on the actual TaskFlow dashboard — layout (Mon), design system (Tue), component patterns (Wed), form (today) — resolve any remaining inconsistencies. |
| 3 | 45 min | **Week 2 checkpoint**: re-run Friday-Week-1's accessibility audit (keyboard nav, screen reader, contrast) against the now-Tailwind version — restyling must not have broken anything from last week. |
| 3 | 15 min | **Wrap-up / demo**: 2–3 students demo their finished TaskFlow dashboard, instructor calls out one place each has a really clean use of the design system. |

**By end of week:** A fully Tailwind-styled, design-system-consistent, still-accessible TaskFlow dashboard with reusable card/nav/form patterns — ready to be rebuilt as React components starting Module 2.

---

## Notes for the Instructor

- **Day 1's "convert, don't redesign" framing matters.** The goal this week is not a prettier dashboard — it's the same dashboard, expressed in a system that scales. If students start redesigning instead of converting, redirect them back to the spec.
- **The Sass/Bootstrap comparison (Day 2) is intentionally brief and non-graded** — recognition, not competency. Don't let it expand into a build exercise; that hour is protected for the design-system work.
- **Thursday's No-AI checkpoint is the most important session of the week.** Resist the urge to rush it to fit more Tailwind content — the critique discussion is where students internalize "AI accelerates me, it doesn't replace my judgment," which is the throughline for the rest of the program's No-AI checkpoints.
- **Friday's re-run accessibility audit is a deliberate regression check**, not busywork — restyling is exactly where accessibility silently breaks (missing focus rings are the most common casualty), and it's a cheap, fast way to prove the point.
