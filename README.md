# AI Product Development: Web Track
## 300-Hour Specialization Curriculum (Post-Core)
### v2 — "One App, Four Build Cycles" Design

**Format:** Monday–Friday, 3 hrs/day → 20 weeks (100 sessions)
**Prerequisite:** 360-hour Foundation Core (Intro to AI Product Dev, Software Systems & Architecture, Software Development with AI, AI Agents & Automation)
**Outcome roles:** Web Developer, Full Stack Developer, Front End Engineer
**Design goal:** genuine competence on small-to-mid scale apps — not just exposure to a checklist of tools.

---

## 1. The Core Design Change

The v1 draft ran five modules, each ending in its own throwaway project — five different demo apps, never revisited. That maximizes topic coverage but minimizes depth: students never debug code they already own, and never see the same class of bug show up twice in a different context, which is where real skill actually forms.

v2 keeps the same five modules and the same 300 hours, but restructures the project work around **one application, rebuilt and extended four times**, plus a **transfer project** at the end to prove the skills generalize rather than got memorized to one codebase.

| | v1 (five separate projects) | v2 (one app, four cycles + transfer) |
|---|---|---|
| Breadth | 5 distinct demo apps | 1 app deepened 4x + 1 new-domain app |
| Repetition | Low — fresh start each module | High — same data model, new constraints each cycle |
| Debugging real code | Only within a 4-week window | Continuous — always debugging code from a prior cycle |
| Risk | Wide but shallow | Deep but narrower domain exposure |
| Best for | Portfolio variety | Actual competence / interview-ready problem solving |

---

## 2. The Spine App: "TaskFlow"

A project/task manager: projects, tasks, users, roles, due dates, filtering/sorting, comments. Chosen because it's simple enough to build fast in Cycle 1, but has enough real structure (relationships, permissions, state) to justify every topic in every module without inventing filler features.

| Cycle | Weeks | Module | What changes | What's held constant (the repetition) |
|---|---|---|---|---|
| 1 — Static UI | 1–4 | Front-End | Built in HTML/CSS/Tailwind/JS/TS against mock data | Core data model: tasks, projects, filters — established once, reused for the rest of the course |
| 2 — React rebuild | 5–8 | React | Same app, same features, rebuilt as React components + client routing + state | Same data shape and feature set — now debugged inside a component/render model instead of raw DOM |
| 3 — Full-stack | 9–12 | Back-End & API | Real Express API + Postgres + auth wired to the Cycle 2 frontend, replacing mock data | Same app, now with real persistence, real users, real permissions |
| 4 — Production | 13–16 | Cloud/DevOps/Security | Dockerized, deployed to AWS, security-hardened (OWASP pass), automated tests added | Same app, now under production constraints (secrets, containers, CI/CD, attack surface) |

**Module 5 (Weeks 17–20) is the transfer test**, not another TaskFlow cycle: students scope and build a different-domain app (inventory tracker, booking system, event manager — instructor-approved) applying the full stack solo, then do a performance/accessibility pass and deploy it. This is where you find out whether the patterns transferred or the student only knew TaskFlow.

---

## 3. Bug Clinic — Recurring Bug Classes Across Cycles

Every Friday closes with a **Bug Clinic**: instructor-seeded broken code (in that week's cycle of TaskFlow) that students must diagnose and fix, not code they wrote themselves. The same root-cause bug categories are deliberately re-seeded in later cycles, in a different technical context each time, so students learn to recognize the *pattern*, not just the fix.

| Bug class | 1st seeded | Recurs (different context) | Why it's a different problem each time |
|---|---|---|---|
| Null/undefined & missing validation | Vanilla JS form (Wk 3) | React props/state (Wk 7) → server-side DB writes (Wk 9) → missing env var crashing a container (Wk 13) | Same root cause, four unrelated failure surfaces |
| Async ordering / race conditions | fetch() ordering (Wk 3) | useEffect stale closures (Wk 5) → concurrent Express requests (Wk 11) → container health-check timing (Wk 13) | Same category, the underlying execution model changes each time |
| State mutation | Direct array/object mutation in React (Wk 6) | Stale cache after a write (Wk 10) → unmemoized re-renders under load (Wk 17) | Same mistake, surfaces as a "bug" early and a "performance problem" later |
| Auth / trust-boundary | Broken JWT logic (Wk 11) | CORS/secrets misconfig on deploy (Wk 14) → seeded SQLi/XSS branch (Wk 15) | Same category of mistake, different exploit each time |
| N+1 / inefficient queries | Seeded in the Postgres+ORM unit (Wk 10) | Reappears at scale in the performance module (Wk 17) | Same query mistake, invisible in isolation, costly under load |
| Off-by-one / boundary errors | Pagination (Wk 12) | — (one deliberate rep; lower priority than the above) | Still a useful category to have hit once |

Bug Clinic days replace what would otherwise be lecture/practice time inside each module's existing hour budget — no extra hours are added, this is a redistribution of the same 60 hours per module.

---

## 4. "No-AI First" Checkpoints

Because this track is explicitly AI-accelerated, there's a real risk of students scaffolding things they don't understand. Each module includes at least one timed, no-assistant checkpoint *before* the AI-accelerated version of the same task, so AI use is amplifying understanding already demonstrated, not replacing it.

| Module | No-AI checkpoint | Then, AI-accelerated version |
|---|---|---|
| 1 | Build a responsive nav + card layout from a spec, no AI tools, 45 min | Same layout, AI-assisted, compare/critique output |
| 2 | Write a component with props/state from scratch, no AI, 45 min | Scaffold an equivalent component with an AI assistant, review for correctness |
| 3 | Write one CRUD endpoint + validation by hand, no AI, 45 min | Scaffold the rest of the CRUD surface with AI, review generated SQL/migrations |
| 4 | Write a Dockerfile from scratch, no AI, 30 min | Use AI to optimize/multi-stage the same Dockerfile, explain every change |

---

## 5. Time Budget (unchanged: 300 hours / 20 weeks)

| Module | Hours | Weeks | Focus | TaskFlow cycle |
|---|---|---|---|---|
| 1. Modern Front-End, AI-Accelerated | 60 | 1–4 | HTML/CSS, Tailwind, JS/TS, responsive & accessible UI | Cycle 1 — Static UI |
| 2. React & Component Architecture | 60 | 5–8 | React, hooks, state, component testing | Cycle 2 — React rebuild |
| 3. Back-End & API Engineering | 60 | 9–12 | Node/Express, REST/auth, Postgres, ORMs | Cycle 3 — Full-stack |
| 4. Cloud, DevOps & Web Security | 60 | 13–16 | Docker, CI/CD, AWS, OWASP, automated QA | Cycle 4 — Production |
| 5. Performance & Transfer Capstone | 60 | 17–20 | Web perf, SEO/accessibility, new-domain solo build | Transfer app |

---

## 6. Module 1 — Modern Front-End, AI-Accelerated (Weeks 1–4, 60h)
**TaskFlow Cycle 1: Static UI**

| Week | Days (M–F) topics |
|---|---|
| 1 | HTML5 semantics & structure → CSS box model, flexbox → CSS Grid → responsive breakpoints/mobile-first → accessibility (ARIA, contrast, keyboard nav) |
| 2 | Tailwind setup & utility workflow → design systems (spacing/typography scale) → component patterns (cards, nav, forms) → **No-AI checkpoint**: build nav+card layout from spec → AI-assisted version + critique |
| 3 | JS ES6+ refresher (arrow fns, destructuring, async/await) → DOM manipulation & events → fetch()/JSON (ties to core) → intro TypeScript → **Bug Clinic 1**: seeded null/undefined + async-ordering bugs in a mock-data form |
| 4 | Forms & validation → animations/transitions → image/perf basics → **TaskFlow Cycle 1 build**: static, mock-data version of TaskFlow (HTML/CSS/Tailwind/TS) → demo/critique |

*Sass and Bootstrap: 30–45 min legacy-recognition comparison in Week 2, not a full unit — Tailwind is the deep skill taught.*

---

## 7. Module 2 — React & Component Architecture (Weeks 5–8, 60h)
**TaskFlow Cycle 2: React rebuild**

| Week | Days (M–F) topics |
|---|---|
| 5 | Why component architecture → JSX & functional components → props & composition → useState → useEffect & side effects → **Bug Clinic 2**: seeded stale-closure bug in a useEffect |
| 6 | Tailwind + component libraries → forms in React (controlled inputs) → lifting state/prop drilling → Context API → client-side routing → **Bug Clinic 3**: seeded direct state-mutation bug |
| 7 | Custom hooks → data fetching patterns (loading/error/empty) → **No-AI checkpoint**: write a component with props/state from scratch → AI-scaffolded equivalent, review |
| 8 | Component testing (RTL basics) → state management at scale (Context vs. Redux/Zustand) → **TaskFlow Cycle 2 build**: rebuild TaskFlow as a React app, same features, same data shape → demo/critique |

---

## 8. Module 3 — Back-End & API Engineering (Weeks 9–12, 60h)
**TaskFlow Cycle 3: Full-stack**

| Week | Days (M–F) topics |
|---|---|
| 9 | Node.js & npm ecosystem → Express fundamentals → routing & middleware → building a REST API from scratch → **No-AI checkpoint**: hand-write one CRUD endpoint + validation |
| 10 | Request validation & error handling → env config/secrets → PostgreSQL connection → SQL fundamentals (CRUD, joins) → ORM (Prisma/Sequelize) → **Bug Clinic 4**: seeded N+1 query + stale-cache bug |
| 11 | Authentication (sessions vs. JWT) → authorization/roles → Mongo vs. Postgres tradeoffs (conceptual, not a parallel build) → schema design for a real feature → AI-scaffolded CRUD/migrations, review generated SQL → **Bug Clinic 5**: seeded broken JWT logic |
| 12 | API docs (OpenAPI/Postman) → rate limiting & pagination → **TaskFlow Cycle 3 build**: wire the Cycle 2 React frontend to a real Express+Postgres backend with auth, replacing mock data → demo/critique |

*Mongo is taught conceptually (schema tradeoffs) rather than as a second parallel database build — this buys back the hours v1 spent building the same CRUD twice in two databases, redirected into repetition on Postgres and into Bug Clinic time.*

---

## 9. Module 4 — Cloud, DevOps & Web Security (Weeks 13–16, 60h)
**TaskFlow Cycle 4: Production**

| Week | Days (M–F) topics |
|---|---|
| 13 | Docker fundamentals: images, containers, Dockerfiles → **No-AI checkpoint**: write a Dockerfile from scratch → AI-optimized multi-stage version, explain every change → containerize TaskFlow → docker-compose for local multi-service dev → **Bug Clinic 6**: seeded missing-env-var container crash + health-check timing bug |
| 14 | AWS foundations: IAM, EC2/ECS or Elastic Beanstalk, S3 → deploy the containerized TaskFlow to AWS → secrets in production → domain/DNS/HTTPS → **Bug Clinic 7**: seeded CORS/secrets misconfig on deploy |
| 15 | Web security: OWASP Top 10 walkthrough → XSS, CSRF, SQL injection — causes & mitigations → secure auth practices, password hashing → dependency/vulnerability scanning → **Bug Clinic 8**: seeded SQLi/XSS branch in TaskFlow, students find and patch it |
| 16 | Automated QA: unit vs. integration vs. e2e → writing tests for TaskFlow's API → intro to Playwright/Cypress → **TaskFlow Cycle 4 build**: fully containerized, tested, deployed, security-reviewed TaskFlow → demo/critique |

---

## 10. Module 5 — Performance & Transfer Capstone (Weeks 17–20, 60h)
**Transfer app: new domain, solo build**

| Week | Days (M–F) topics |
|---|---|
| 17 | Web performance: Core Web Vitals, Lighthouse audits → bundle size & code splitting → caching strategies → asset optimization → SEO fundamentals → **Bug Clinic 9**: seeded unmemoized-re-render performance bug (same root cause as Bug Clinic 3, now a perf problem not a correctness bug) → apply a performance pass to TaskFlow itself |
| 18 | Accessibility audit tools & remediation → **transfer project kickoff**: student scopes a new-domain app (inventory tracker, booking system, event manager, etc.), wireframes it, chooses stack → architecture review 1:1 with instructor |
| 19 | Transfer app build sprint (front end + back end + DB) → daily stand-ups/soft-skills practice (status updates, unblocking, feedback) → mid-sprint check-in & scope triage |
| 20 | Transfer app build sprint (deployment, testing, polish) → performance & accessibility pass → deploy to AWS → **Demo day**: present both TaskFlow (depth) and the transfer app (breadth/transfer) to instructors/peers, portfolio-ready writeup for both |

*Soft skills are embedded as daily stand-ups and critique days across every cycle, not a standalone unit — reinforced most heavily here in the solo sprint.*

---

## 11. Legacy Topic → New Home Mapping

| Legacy topic (660h program) | Where it lives now | Why |
|---|---|---|
| Terminal Commands | Core (Software Dev with AI) | Already taught before the Web track begins |
| Folder Architecture | Core | Same |
| Git / GitHub | Core | Reinforced via daily commits across every TaskFlow cycle |
| HTML/CSS | Module 1 | Full unit, TaskFlow Cycle 1 |
| Tailwind CSS | Module 1 | Primary styling system, taught in depth |
| Bootstrap | Module 1 (brief) | Legacy-recognition only |
| Sass | Module 1 (brief) | Same — Tailwind reduces the need for a preprocessor |
| JavaScript | Module 1 | Refresher building on core's coding course |
| TypeScript | Modules 1–3 | Introduced front end, reinforced back end |
| React | Module 2 | Full unit, TaskFlow Cycle 2 |
| Angular | Conceptual overview only | Cut from hands-on build time — one framework deeply beats two shallowly |
| Node / Express | Module 3 | Full unit, TaskFlow Cycle 3 |
| MongoDB | Module 3 (conceptual) | Schema-tradeoff discussion, not a parallel build — hours redirected to repetition/Bug Clinics |
| Postgres | Module 3 | Primary relational DB, used through Cycles 3–4 and the transfer app |
| Docker | Module 4 | Unified deployment-focused unit, TaskFlow Cycle 4 |
| Automated QA | Module 4 | Unit + e2e tests, applied to TaskFlow directly |
| AWS foundations | Module 4 | Full deploy pipeline, reused for the transfer app |
| Web Security | Module 4 | OWASP-based unit with a seeded, patchable vulnerability |
| Soft Skills | Embedded throughout | Stand-ups, critique days, demo day |

---

## 12. Trade-offs, Stated Plainly

- **Less portfolio variety.** Students finish with one deeply-built app (TaskFlow, 4 iterations) and one transfer app — not five distinct demos. If the program's marketing depends on a varied portfolio, this is the cost.
- **Domain narrowness.** All the deep repetition happens inside a task-manager domain. The transfer project in Module 5 is the safeguard against "only knows TaskFlow," but it's a single data point, not five.
- **Mongo is shallower** than in v1 — conceptual only, no hands-on build. Fine if the goal is Postgres depth; revisit if employers in your placement pipeline specifically want Mongo experience.
- **Bug Clinics require real instructor prep** — someone has to deliberately author and seed each broken-code scenario ahead of each session. This is the highest-prep-cost part of the redesign and the part most likely to get skipped under time pressure; it's also the part doing the most work for the "super competent" goal, so it shouldn't be the first thing cut if the course runs long.
- **Capstone/transfer window is still 2 weeks (Weeks 19–20).** Same tightness noted in v1 — worth watching if Module 5 pacing slips.
