# Module 1, Week 3 — Detailed Daily Outline
## JavaScript Refresher, DOM & Events, Fetch/JSON, TypeScript Survival Basics, Bug Clinic 1

**Context:** TaskFlow's dashboard is now a fully Tailwind-styled, design-system-consistent, accessible static skeleton (Week 2) — but it's still just HTML with hardcoded content. This week makes it *dynamic*: data comes from a mock JSON source via `fetch()`, rendered into the DOM with JavaScript, with just enough TypeScript to read/write typed code before Module 2 gives TS its real depth.

**Week deliverable:** TaskFlow's dashboard and a single-project detail view, both rendering from a mock JSON data file via `fetch()` and DOM manipulation (no framework yet — that's Module 2), with basic client-side interactivity (open a project, filter tasks), and the week's Bug Clinic bugs found and fixed in the group's own code.

---

## Day 1 (Monday) — JavaScript ES6+ Refresher

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: arrow functions vs. function declarations (and the `this`-binding difference that actually matters), destructuring (objects and arrays), template literals, spread/rest syntax. Framed explicitly as "refresher" — students saw this in the core's coding course; this is fluency, not first exposure. |
| 1 | 45 min | **Direct instruction**: ES modules — `import`/`export`, why splitting code into modules matters, default vs. named exports. |
| 2 | 60 min | **Hands-on lab**: refactor a messy, repetitive vanilla-JS file (nested callbacks, repeated object literals) using destructuring, spread, and template literals — same behavior, cleaner code. |
| 3 | 45 min | **Applied**: set up TaskFlow's JS file structure — a `data.js`/`data.json` module, a `render.js` module, an `app.js` entry point — establishing the module boundaries that will matter once fetch and rendering logic get added Wednesday. |
| 3 | 15 min | **Wrap-up**: quick check — can each student explain, in one sentence, why their code is now split into modules instead of one file? |

**By end of day:** Clean, modern JS syntax fluency confirmed; TaskFlow's JS is organized into modules ready to hold data-fetching and rendering logic.

---

## Day 2 (Tuesday) — Async/Await, Promises, DOM Manipulation & Events

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: Promises (pending/resolved/rejected), `.then()` chains, then `async`/`await` as the readable version of the same thing, `try`/`catch` for error handling. |
| 1 | 45 min | **Direct instruction**: DOM manipulation (`querySelector`, `createElement`, `appendChild`, `classList`), event handling (`addEventListener`, event delegation — why delegation matters once elements are dynamically rendered, not just present in static HTML). |
| 2 | 60 min | **Hands-on lab**: build a small interactive list (add/remove/toggle items) using only DOM APIs and event delegation — no framework, no libraries. |
| 3 | 45 min | **Applied**: add interactivity to TaskFlow's static dashboard — clicking a project card should reveal/navigate to that project's task list (client-side, no real routing yet), using event delegation so it works even for cards that don't exist yet in the DOM. |
| 3 | 15 min | **Wrap-up**: instructor asks one student to explain why event delegation was necessary here, not just convenient. |

**By end of day:** TaskFlow's dashboard responds to clicks; students understand async syntax well enough to consume a fetch call tomorrow without it being new territory.

---

## Day 3 (Wednesday) — Fetch, JSON & Wiring Real(ish) Data

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: `fetch()` syntax, working with the Response object, `.json()`, HTTP status handling, and — explicitly tying back to the core's Systems & Architecture course — a reminder of the request/response lifecycle they already learned, now seen from the client side. |
| 1 | 45 min | **Direct instruction + demo**: loading/error/empty states as first-class UI states, not afterthoughts — instructor demos a fetch that's slow (loading state visible), one that fails (error state), and one that returns nothing (empty state), and why all three need explicit handling. |
| 2 | 60 min | **Hands-on lab**: given a public mock JSON API (or a local `data.json` served statically), fetch and render a list of items with all three states (loading/error/empty) handled. |
| 3 | 45 min | **Applied**: replace TaskFlow's hardcoded HTML content with data fetched from a local `data.json` file — projects and tasks now render dynamically, with loading/error/empty states visible in the UI, not just handled silently in code. |
| 3 | 15 min | **Wrap-up**: instructor breaks the JSON file's shape live (renames a field) — students watch what happens with no type-checking in place yet. This is the pain point Thursday's TypeScript lesson exists to solve. |

**By end of day:** TaskFlow's dashboard is data-driven from a mock JSON source, with visible loading/error/empty states. Students have just watched, firsthand, what a shape mismatch does with no types — motivation for Thursday.

---

## Day 4 (Thursday) — TypeScript Survival Basics

| Block | Time | Activity |
|---|---|---|
| 1 | 45 min | **Direct instruction**: primitive types (`string`, `number`, `boolean`), typing function parameters and return values, typing a plain object shape with an `interface` or `type`. Explicitly scoped as "just enough to read and write typed code" — generics, discriminated unions, and typed React patterns are Module 2's job, not this week's. |
| 1 | 45 min | **Guided demo**: instructor converts yesterday's `data.js`/fetch code to TypeScript live — typing the shape of a `Project` and a `Task`, typing the function that renders them, and showing how yesterday's "break the JSON shape" trick now gets caught at compile time instead of failing silently at runtime. |
| 2 | 60 min | **Hands-on lab**: convert a small vanilla-JS fetch-and-render exercise to TypeScript — define interfaces for the data shape, type the fetch function's return, type the render function's parameters. |
| 3 | 45 min | **Applied**: convert TaskFlow's `data.js` module and rendering functions to TypeScript — `Project` and `Task` interfaces, typed fetch function, typed render functions. |
| 3 | 15 min | **Wrap-up**: instructor repeats yesterday's "break the JSON shape" experiment — this time TypeScript catches it before the code even runs. Direct before/after comparison. |

**By end of day:** TaskFlow's data layer is fully typed. Students have a concrete, felt reason TypeScript exists (Wednesday's break vs. today's catch), not just abstract syntax rules.

---

## Day 5 (Friday) — Bug Clinic 1

| Block | Time | Activity |
|---|---|---|
| 1 | 30 min | **Framing**: this is the first Bug Clinic of the program — students are debugging *instructor-seeded* broken code, not their own, and should treat it like a real bug report: reproduce, isolate, fix, verify. No AI assistant for the first diagnosis pass. |
| 1 | 60 min | **Bug Clinic 1**: students receive a version of the mock-data TaskFlow form/list with two seeded bugs: (1) a null/undefined access bug — code assumes data has loaded before it has, causing a crash or blank render; (2) an async-ordering bug — two fetches resolve out of order, so the UI briefly (or persistently) shows stale/wrong data. Students diagnose and fix both, documenting in a few sentences what the root cause was and how they found it. |
| 2 | 45 min | **Group debrief**: 3–4 students walk the class through their diagnosis process — instructor draws out the pattern-level lesson (assuming data exists before confirming it; assuming async operations resolve in the order they were started) rather than just the specific fix, since these same root causes reappear in different forms in Modules 2–4. |
| 3 | 45 min | **Applied**: students audit their *own* TaskFlow code from Wednesday/Thursday for the same two bug classes — do they have any unguarded data access before load completes? Any unhandled fetch ordering assumptions? Fix anything found. |
| 3 | 15 min | **Week wrap-up**: quick recap of the week — JS fluency → DOM/events → real data via fetch → typed data → now, debugging when data-fetching goes wrong. Preview Week 4: forms, validation, and the Cycle 1 build/demo. |

**By end of week:** Students have direct experience with the two bug classes (null/undefined access, async ordering) that resurface throughout the program — first here, then again in React's `useEffect` (Module 2), server-side writes (Module 3), and container startup timing (Module 4).

---

## Notes for the Instructor

- **Wednesday's "break the JSON shape" moment and Thursday's "TypeScript catches it" callback are the emotional core of this week** — don't skip either demo for time. The felt contrast is what makes TypeScript's value obvious rather than assumed.
- **Bug Clinic 1 should be genuinely debugged, not pattern-matched from memory.** If students have seen the exact bug before (e.g., from a tutorial), consider varying the surface content (different data, different specific line) so they're exercising diagnosis, not recall.
- **The group debrief matters more than the fix itself.** The goal is for students to walk away recognizing "unguarded access before load" and "assumed resolution order" as categories they'll watch for everywhere — the specific TaskFlow bug is just the vehicle.
- **This week's TypeScript is intentionally shallow** — if a student asks about generics or advanced typing, it's fine to say "that's coming in Module 2 with real motivation" rather than going down that path now.
