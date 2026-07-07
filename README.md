# AI Product Development: Web Track
## 300-Hour Specialization Curriculum (Post-Core)
### v5 — 5 Modules, React-Weighted, "One App, Rebuilt" Design

**Format:** Monday–Friday, 3 hrs/day → 20 weeks (100 sessions)
**Prerequisite:** 360-hour Foundation Core (Intro to AI Product Dev, Software Systems & Architecture, Software Development with AI, AI Agents & Automation)
**Outcome roles:** Web Developer, Full Stack Developer, Front End Engineer
**Design goal:** genuine competence on small-to-mid scale apps — not just exposure to a checklist of tools.

---

## 1. Structure at a Glance

| Module | Hours | Weeks | Topics |
|---|---|---|---|
| 1. Modern Front-End, AI-Accelerated | 60 | 1–4 | HTML/CSS, Tailwind, JS/TS, responsive & accessible UI |
| 2. React & Component Architecture | 90 | 5–10 | React, hooks, state, component testing |
| 3. Back-End & API Engineering | 60 | 11–14 | Node/Express, REST/auth, Postgres, ORMs |
| 4. Cloud, DevOps & Web Security | 60 | 15–18 | CI/CD, OWASP, AWS, Automated QA, SEO/Accessibility/Web Performance |
| 5. Capstone | 30 | 19–20 | App build → deploy → demo day |
| **Total** | **300** | **20** | |

At 15 hrs/week (3hrs × 5 days), every module's hours divide evenly into its week range — no overlap, no orphaned time.

---

## 2. Why This Weighting

React carries the extra 30 hours because it's the module everything downstream depends on — the Back-End module wires a real API into the React app built here, and the Capstone reuses these same patterns solo. It's also historically where students are weakest in interviews (state, hooks, re-render behavior) and where AI-assisted scaffolding is most tempting to lean on before the underlying concept is actually understood.

The cost: Front-End's 60 hours has to cover HTML/CSS/Tailwind/JS/TypeScript/accessibility without a dedicated deep-dive week for TypeScript or accessibility specifically — those get woven into the regular flow (Weeks 1 and 3 below) rather than getting their own week. If a cohort tends to arrive shakier on those fundamentals than on React, that's the signal to revisit this balance again.

---

## 3. The Spine App: "TaskFlow"

One app (a project/task manager — projects, tasks, users, roles, due dates, filtering, comments) rebuilt and extended through each module, so students continuously debug and extend code they already own rather than starting fresh each time. Module 5 is a **transfer test**: a new-domain app built solo, proving the patterns generalized beyond TaskFlow.

| Cycle | Module | Weeks | What changes | What's held constant |
|---|---|---|---|---|
| 1 — Static UI | 1 | 1–4 | HTML/CSS/Tailwind/TS against mock data | Core data model established once, reused throughout |
| 2 — React rebuild | 2 | 5–10 | Same features, rebuilt as React components + routing + state | Same data shape/features, debugged in a new rendering model |
| 3 — Full-stack | 3 | 11–14 | Real Express API + Postgres + auth replaces mock data | Same app, now with real persistence and permissions |
| 4 — Production | 4 | 15–18 | Dockerized, deployed to AWS, security-hardened, tested | Same app, now under production constraints |
| Transfer | 5 | 19–20 | New domain, solo build, full stack applied independently | Same patterns/stack, proving transfer beyond TaskFlow |

---

## 4. Module 1 — Modern Front-End, AI-Accelerated (Weeks 1–4, 60h)
**TaskFlow Cycle 1: Static UI**

| Week | Days (M–F) topics |
|---|---|
| 1 | HTML5 semantics & structure → CSS box model, flexbox → CSS Grid → responsive breakpoints/mobile-first → accessibility (ARIA, contrast, keyboard nav) |
| 2 | Tailwind setup & utility workflow → design systems (spacing/typography scale) → component patterns (cards, nav, forms) → **No-AI checkpoint**: build nav+card layout from spec → AI-assisted version + critique |
| 3 | JS ES6+ refresher (arrow fns, destructuring, async/await) → DOM manipulation & events → fetch()/JSON (ties to core) → TypeScript survival basics: primitive types, typing function params/returns, typing a plain object shape (just enough to read and write typed code — real depth comes in Module 2) → **Bug Clinic 1**: seeded null/undefined + async-ordering bugs in a mock-data form |
| 4 | Forms & validation → animations/transitions → image/perf basics → **TaskFlow Cycle 1 build**: static, mock-data version of TaskFlow (HTML/CSS/Tailwind/TS) → demo/critique |

*Sass and Bootstrap: brief legacy-recognition comparison in Week 2, not a full unit — Tailwind is the deep skill taught. TypeScript in Week 3 is intentionally shallow — just enough vocabulary (types, function signatures, object shapes) to not be lost in Module 2, where typed props, typed hooks, and typed API responses give TS a much more motivated, concrete treatment. Accessibility stays woven through Week 1 rather than getting a standalone week, given the 60-hour budget.*

---

## 5. Module 2 — React & Component Architecture (Weeks 5–10, 90h)
**TaskFlow Cycle 2: React rebuild**

| Week | Days (M–F) topics |
|---|---|
| 5 | Why component architecture → JSX & functional components → **typed props** (interfaces for component props from day one) → composition → **typed useState** (generics: `useState<Task[]>`) → useEffect & side effects → **Bug Clinic 2**: seeded stale-closure bug in a useEffect |
| 6 | Tailwind + component libraries → forms in React (**typed controlled inputs & typed form event handlers**) → lifting state/prop drilling (typed shared state) → Context API (**typed context + typed provider**) → client-side routing (typed route params) → **Bug Clinic 3**: seeded direct state-mutation bug |
| 7 | Custom hooks (deep dive, **typed hook parameters and typed return values/tuples**) → extracting shared logic → **No-AI checkpoint**: write a custom hook from scratch, fully typed → AI-scaffolded equivalent, review |
| 8 | Data fetching patterns (loading/error/empty states, **typed with a discriminated union** so each state is type-safe) → connecting to a real REST API (**typing the API response shape**) → state management at scale (Context vs. Redux/Zustand, typed either way) → when each is the right call → **Typed React checkpoint**: take an existing Cycle 2 component and add proper typing to its props, state, and API response shape — no-AI-first pass, then AI-assisted typing of a harder case (generics, discriminated unions) |
| 9 | Component testing (React Testing Library, typed test utilities) → testing hooks and async components → **Bug Clinic 4 (extra pass)**: seeded unmemoized-re-render bug — same root cause as Bug Clinic 3, now framed as a performance issue, foreshadowing Module 4 |
| 10 | Advanced patterns review → **TaskFlow Cycle 2 build**: rebuild TaskFlow fully as a React app, fully typed, same features, same data shape → demo/critique |

*The extra weeks (7–9) go to custom hooks depth, data-fetching patterns, and a second Bug Clinic pass — the areas most likely to be shallow in a compressed 60-hour version, and the ones most predictive of interview performance. TypeScript isn't a separate topic here — it's woven into every React concept as it's taught (typed props, typed hooks, typed API responses), which is closer to how it's actually used on the job than teaching TS as its own unit. The Week 8 checkpoint is the one place typing is explicitly assessed rather than just assumed to have soaked in.*

---

## 6. Module 3 — Back-End & API Engineering (Weeks 11–14, 60h)
**TaskFlow Cycle 3: Full-stack**

| Week | Days (M–F) topics |
|---|---|
| 11 | Node.js & npm ecosystem → Express fundamentals → routing & middleware → building a REST API from scratch → **No-AI checkpoint**: hand-write one CRUD endpoint + validation |
| 12 | Request validation & error handling → env config/secrets → PostgreSQL connection → SQL fundamentals (CRUD, joins) → ORM (Prisma/Sequelize) → **Bug Clinic 5**: seeded N+1 query + stale-cache bug |
| 13 | Authentication (sessions vs. JWT) → authorization/roles → Mongo vs. Postgres tradeoffs (conceptual) → schema design for a real feature → AI-scaffolded CRUD/migrations, review generated SQL → **Bug Clinic 6**: seeded broken JWT logic |
| 14 | API docs (OpenAPI/Postman) → rate limiting & pagination → **TaskFlow Cycle 3 build**: wire the Cycle 2 React frontend to a real Express+Postgres backend with auth → demo/critique |

*Mongo stays conceptual (schema tradeoffs) rather than a second parallel build — hours redirected to Postgres depth and Bug Clinic time.*

---

## 7. Module 4 — Cloud, DevOps & Web Security (Weeks 15–18, 60h)
**TaskFlow Cycle 4: Production**

| Week | Days (M–F) topics |
|---|---|
| 15 | Docker fundamentals: images, containers, Dockerfiles → **No-AI checkpoint**: write a Dockerfile from scratch → AI-optimized multi-stage version, explain every change → containerize TaskFlow → docker-compose for local dev → **Bug Clinic 7**: seeded missing-env-var container crash + health-check timing bug |
| 16 | AWS foundations: IAM, EC2/ECS or Elastic Beanstalk, S3 → deploy the containerized TaskFlow to AWS → secrets in production → domain/DNS/HTTPS → CI/CD with GitHub Actions → **Bug Clinic 8**: seeded CORS/secrets misconfig on deploy |
| 17 | Web security: OWASP Top 10 walkthrough → XSS, CSRF, SQL injection — causes & mitigations → secure auth practices, password hashing → dependency/vulnerability scanning → **Bug Clinic 9**: seeded SQLi/XSS branch, students find and patch it |
| 18 | Automated QA (unit/integration/e2e) → SEO fundamentals → accessibility audit tools → Core Web Vitals & performance basics (including a revisit of the Module 2 re-render bug, now framed as a performance issue) → **TaskFlow Cycle 4 build**: fully containerized, tested, deployed, security-reviewed, performance-audited TaskFlow → demo/critique |

*Week 18 is dense — QA, SEO, accessibility, and performance all land in the same week as that module's build/demo. If it runs short, trim SEO/performance depth here first; students get a second performance/accessibility pass during the Capstone.*

---

## 8. Module 5 — Capstone (Weeks 19–20, 30h)
**Transfer app: new domain, solo build**

| Week | Days (M–F) topics |
|---|---|
| 19 | Capstone kickoff: student scopes a new-domain app (inventory tracker, booking system, event manager, etc.), wireframes it, chooses stack → architecture review 1:1 with instructor → build sprint begins (front end + back end + DB) → daily stand-ups (status updates, unblocking, feedback) |
| 20 | Build sprint continues (deployment, testing, polish) → performance & accessibility pass → deploy to AWS → **Demo day**: present both TaskFlow (depth) and the transfer app (breadth/transfer) to instructors/peers, portfolio-ready writeup for both |

*Soft skills aren't a standalone lecture block — they're the daily stand-ups and critique days carried through every module's build week, culminating in the demo-day presentation here.*

---

## 9. Legacy Topic → New Home Mapping

| Legacy topic (660h program) | Where it lives now | Why |
|---|---|---|
| Terminal Commands | Core (Software Dev with AI) | Already taught before the Web track begins |
| Folder Architecture | Core | Same |
| Git / GitHub | Core | Reinforced via daily commits across every TaskFlow cycle |
| HTML/CSS | Module 1 | Full unit, TaskFlow Cycle 1 |
| Tailwind CSS | Module 1 | Primary styling system, taught in depth |
| Bootstrap / Sass | Module 1 (brief) | Legacy-recognition only |
| JavaScript / TypeScript | JS in Module 1; TS survival basics Module 1 Wk 3, real TS depth woven through Module 2 | TS is deliberately shallow in Module 1 (just enough vocabulary) and gets its real depth attached to typed props/hooks/API responses in Module 2, where the use is concrete rather than abstract |
| React | Module 2 | Full unit, extra depth via the added 30h, TaskFlow Cycle 2 |
| Angular | Conceptual overview only | Cut from hands-on build time |
| Node / Express | Module 3 | Full unit, TaskFlow Cycle 3 |
| MongoDB | Module 3 (conceptual) | Schema-tradeoff discussion, not a parallel build |
| Postgres | Module 3 | Primary relational DB, used through Cycles 3–4 and the transfer app |
| Docker | Module 4 | Unified deployment-focused unit, TaskFlow Cycle 4 |
| Automated QA | Module 4 | Unit + e2e tests, applied to TaskFlow directly |
| AWS foundations / CI/CD | Module 4 | Full deploy pipeline, reused for the transfer app |
| Web Security | Module 4 | OWASP-based unit with a seeded, patchable vulnerability |
| SEO / Accessibility / Performance | Module 1 (basics) + Module 4 + Capstone | Basic accessibility in Module 1; SEO/performance depth introduced Week 18, reinforced in the Capstone |
| Soft Skills | Embedded throughout + Capstone | Stand-ups, critique days, demo day |

---

## 10. Trade-offs, Stated Plainly

- **Front-End's 60 hours only gives TypeScript a survival-level treatment** (Week 3) — real TS depth is deferred to Module 2, attached to typed props/hooks/API responses. This is a deliberate bet that TS is better learned in a motivated, concrete context (typing real React code) than as abstract syntax up front. If students arrive at Week 5 without even the survival basics solid, that's the signal to add a review day rather than assume Module 2 will cover the gap.
- **Accessibility gets no dedicated deep-dive week either** — it's woven into Week 1 only. Watch this in the first cohort; if it's too shallow, that's the other candidate for borrowing hours back from React.
- **Week 18 is still dense** — QA, SEO, accessibility, and performance all share one week with that module's build/demo. Trim SEO/performance depth here first if needed; the Capstone provides a second pass.
- **Less portfolio variety** than a five-separate-projects design — one deeply-built app (TaskFlow) plus one transfer app, not five distinct demos.
- **Mongo is conceptual only** — fine for Postgres-focused hiring pipelines, worth revisiting if employers specifically want Mongo experience.
- **Bug Clinics require real instructor prep** (someone has to author and seed each broken-code scenario ahead of time) — the highest-prep-cost part of this design, and also the part doing the most work toward "competent," so it shouldn't be the first thing cut under time pressure.
