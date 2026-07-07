# Module 1, Week 4 — Detailed Daily Outline
## Forms & Validation, Animations & Transitions, Images & Performance, TaskFlow Cycle 1 Build

**Context:** TaskFlow is now Tailwind-styled (Week 2), data-driven and typed (Week 3), with the null/undefined and async-ordering bug classes already debugged once. This final week of Module 1 adds the last two front-end skills (form validation, motion/animation, image/perf basics) and then spends two full days building and demoing the complete Cycle 1 deliverable — the static, mock-data version of TaskFlow that Module 2 will rebuild in React.

**Week deliverable:** TaskFlow Cycle 1 — a complete, static, mock-data-driven, typed, accessible, responsive, Tailwind-styled task manager with working forms, validation, subtle motion, and optimized images — demoed and critiqued on Friday.

---

## Day 1 (Monday) — Forms & Validation

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: native HTML5 form validation (`required`, `pattern`, `type="email"`, `minlength`), the Constraint Validation API, and why native validation should be the first line of defense, not an afterthought to JS validation. |
| 1 | 45 min | **Direct instruction**: custom validation logic in TypeScript — validating on submit vs. on blur vs. as-you-type, writing typed validation functions, and accessible error messaging (`aria-invalid`, `aria-describedby`, associating error text with its input — tying directly back to Week 1's accessibility work). |
| 2 | 60 min | **Hands-on lab**: build a signup-style form with 4 fields (text, email, password, select), native + custom validation, accessible inline error states for each. |
| 3 | 45 min | **Applied**: build TaskFlow's "new task" and "new project" forms with full validation (required fields, typed input shapes, accessible error messaging matching the form pattern established in Module 1 Week 2). |
| 3 | 15 min | **Wrap-up**: quick screen-reader check — do the error messages actually get announced when a field fails validation? |

**By end of day:** TaskFlow's task/project creation forms are validated, typed, and accessible on error.

---

## Day 2 (Tuesday) — CSS Animations & Transitions

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: CSS transitions (`transition-property`, `duration`, `easing`) for simple state changes (hover, focus, expand/collapse) vs. `@keyframes` for more complex multi-step animations. |
| 1 | 45 min | **Direct instruction**: `prefers-reduced-motion` and why motion is an accessibility concern, not just a design flourish — some users get genuinely nauseated or disoriented by unnecessary motion, and this media query is the standard way to respect that. |
| 2 | 60 min | **Hands-on lab**: build a card hover-lift effect, a smooth expand/collapse for a details panel, and a subtle fade-in for newly added list items — each respecting `prefers-reduced-motion`. |
| 3 | 45 min | **Applied**: add restrained motion to TaskFlow — card hover states, a smooth open/close for the task detail view, a brief fade when a new task is added — all gated behind `prefers-reduced-motion`. |
| 3 | 15 min | **Wrap-up**: toggle "reduce motion" in OS settings and confirm TaskFlow's animations actually respect it. |

**By end of day:** TaskFlow has restrained, purposeful motion that's disabled correctly for users who need it disabled.

---

## Day 3 (Wednesday) — Images & Web Performance Basics

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: modern image formats (WebP/AVIF vs. JPEG/PNG), `srcset`/`sizes` recap from Week 1's responsive work, native lazy loading (`loading="lazy"`), and why image weight is usually the single biggest lever on page performance. |
| 1 | 45 min | **Direct instruction + demo**: first Lighthouse audit — instructor runs it against TaskFlow as it currently stands, reads the report together (performance score, specific flagged issues), and explains Core Web Vitals at a conceptual level (this gets full depth in Module 4, Week 18 — today is just enough to read a report and act on the obvious wins). |
| 2 | 60 min | **Hands-on lab**: given an unoptimized page (huge unconverted images, no lazy loading), students optimize it and re-run Lighthouse to confirm measurable improvement. |
| 3 | 45 min | **Applied**: optimize TaskFlow's images (convert formats, add lazy loading where appropriate, confirm responsive `srcset` still works), then run Lighthouse against TaskFlow and fix anything else flagged that's a quick win. |
| 3 | 15 min | **Wrap-up**: each student reports their before/after Lighthouse performance score. |

**By end of day:** TaskFlow's images are optimized and lazy-loaded, and students have run and acted on their first Lighthouse audit.

---

## Day 4 (Thursday) — TaskFlow Cycle 1 Build (Integration Day)

| Block | Time | Activity |
|---|---|---|
| 1 | 15 min | **Framing**: today and tomorrow morning are integration time — no new topics. The goal is one coherent, working app, not four separate weeks bolted together. |
| 1 | 30 min | **Planning**: each student reviews their TaskFlow code against a checklist covering every Module 1 topic (semantic HTML, responsive layout, Tailwind design system, component pattern consistency, typed data layer, working forms with validation, restrained accessible motion, optimized images) and identifies gaps. |
| 2 | 60 min | **Build sprint**: close gaps identified in planning — this is unstructured build time, instructor circulates for 1:1 troubleshooting. |
| 3 | 60 min | **Build sprint (continued)**: same, with a checkpoint at the 30-minute mark — instructor does a room-wide accessibility spot-check (keyboard nav, one screen-reader pass per student) since this is the last chance to catch regressions before tomorrow's demo. |

**By end of day:** TaskFlow Cycle 1 is functionally complete; any remaining polish is tomorrow morning's job, not new work.

---

## Day 5 (Friday) — TaskFlow Cycle 1 Demo & Critique

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Final polish**: last build time — fix anything found in Thursday's spot-check, final self-review against the Module 1 checklist. |
| 1 | 45 min | **Demo prep**: students prepare a 2-minute walkthrough of TaskFlow Cycle 1 — what it does, one design-system decision they're proud of, one bug (from Bug Clinic 1 or otherwise) they had to fix along the way. |
| 2 | 60 min | **Demo & critique, round 1**: half the class demos (2 min each) to the full group; instructor and peers give brief structured feedback (one thing working well, one thing to watch for in the Cycle 2 rebuild). |
| 3 | 45 min | **Demo & critique, round 2**: remaining students demo. |
| 3 | 15 min | **Module 1 close-out**: instructor previews Module 2 — this exact app, same features, same data shape, gets rebuilt in React starting Monday, and everything built this month (semantics, Tailwind, typed data, forms, accessibility) is about to get a new, more powerful expression rather than being left behind. |

**By end of week:** TaskFlow Cycle 1 is complete, demoed, and critiqued. Every student has a working static/typed/accessible task manager as their Module 1 artifact — and a clear sense of what's carrying forward into React.

---

## Notes for the Instructor

- **Thursday and Friday morning are deliberately unstructured build time**, not filler — this is where students discover what they half-understood from the four weeks of new material, and it's the last checkpoint before Module 2 assumes this foundation is solid.
- **The demo's "one bug you had to fix" requirement is intentional**, not just show-and-tell — it reinforces the Bug Clinic habit of narrating root cause, not just the fix, in front of peers.
- **The Lighthouse audit on Wednesday is intentionally shallow** — this is a first exposure, not the real performance unit (that's Module 4, Week 18). Resist the urge to go deep on Core Web Vitals metrics here; the goal is just "read a report, act on the obvious wins."
- **Friday's close-out framing matters**: students should leave Module 1 seeing React as "a more powerful way to do what I already built," not "starting over." That framing is what makes the TaskFlow-rebuild structure pay off across the rest of the program.
