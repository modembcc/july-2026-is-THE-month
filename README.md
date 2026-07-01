# 4-Week Sprint Plan v3 — 2 Projects in 2 Weeks + Project 3 + Launch

**Goal:** 3 portfolio-ready projects, then one confident networking/interview push in week 4.

**What changed from v2:** No networking until there's something to show. Esports Tracker (originally 2 weeks) compresses to 1 week — its tasks are boilerplate-heavy (CRUD, EF Core, Docker, deploy), which is exactly where AI drafting saves the most time. Sake Search keeps its original pace since it's new-language learning — AI speeds up typing, not understanding. Weeks 3–4 open up for a new project + a real launch.

**Schedule:** Wed → Mon = build days. Tuesday = review & plan.

---

## Weeks 1–2: Build Mode (No Networking)

100% focus on shipping. LeetCode + build + push, same as always. Networking resumes in Week 3 once you've got projects to point people to.

### Week 1 — July 1–7: Esports Odds & Integrity Tracker (full stack, compressed)

Merging the original two-week plan into one — lean hard on AI for scaffolding/config, and still do the review/explain-back step on everything so you can defend it later.

**Wed July 1 — Setup + Data Model**
- Install .NET SDK, PostgreSQL, Docker Desktop, editor
- Create + pin both GitHub repos (yes, scaffold the Sake repo too, just don't touch it yet)
- Scaffold ASP.NET Web API, design schema (Teams/Matches/Odds/Markets) **[hand-write the schema]**
- EF Core + Npgsql setup, first migration **[AI-fast]**

**Thu July 2 — Endpoints + External Data**
- CRUD endpoints for Teams/Matches, proper status codes/validation **[AI-fast draft, you fix edge cases]**
- Pick an esports API (PandaScore/Riot/OpenDota), background job to pull match data **[AI-fast]**
- Test with curl/Postman

**Fri July 3 — Odds + Anomaly Detection**
- Odds API integration, `GET /matches/{id}/odds` **[AI-fast]**
- Anomaly logic: odds shift > X% in Y hours **[hand-write — your headline interview topic]**
- `GET /matches/anomalies`, 2 unit tests

**Sat July 4 — Frontend Scaffold + Visualization**
- React (Vite + TS): navbar, match list, match detail **[AI-fast scaffold]**
- Odds-over-time line chart, crowd confidence meter **[AI-fast chart boilerplate]**

**Sun July 5 — Anomaly Dashboard + Docker**
- Dashboard page with filtering and suspicion indicators **[AI-fast]**
- Dockerfiles for API + frontend, docker-compose.yml **[AI-fast — read every line]**
- Verify full stack runs with `docker-compose up`

**Mon July 6 — Deploy + Document**
- Deploy to Railway/Render/Azure free tier, env vars set properly
- README overhaul: description, screenshots, tech stack, how to run, live link **[AI drafts structure, you write "why I built this"]**
- Clean commit history

**Tue July 7 — Sprint Review**
- Fully deployed and documented? Can you demo and explain every decision unaided?
- Retro: what did AI save the most time on? What took just as long as expected?
- Mental shift: Go tomorrow

### Week 2 — July 8–14: Sake Search (Go) — original pace kept

This one stays close to the original timeline. New language, new paradigms (goroutines, TUI) — worth the full week to actually absorb it, not just generate it.

**Wed July 8 — Go Day 1**
- "A Tour of Go" (2–3 hrs) **[hand-write along with it]**
- Hello-world CLI with a flag, first commit

**Thu July 9 — API Research & Client**
- Pick a data source or plan a curated local JSON dataset **[hand-write the decision]**
- HTTP client + JSON parsing into structs **[AI-fast, but read the Go idioms closely]**

**Fri July 10 — Core Search + TUI**
- Search with partial/fuzzy matching **[hand-write — likely interview topic]**
- Bubble Tea TUI for interactive experience **[AI-fast]**

**Sat July 11 — Anime Reference Mode**
- Local dataset mapping drinks to anime appearances
- `--anime`, `--episode`, `--appearances` commands **[AI-fast for data structure, hand-write lookup logic]**

**Sun July 12 — SG Availability**
- Research where Japanese alcohol is sold in SG (Don Don Donki, liquor shops, online)
- Availability/pricing module, currency formatting **[AI-fast]**

**Mon July 13 — Translation & Polish**
- Translation layer, `--lang jp` flag **[AI-fast]**
- Tests for search/translation/availability, build the binary

**Tue July 14 — Sprint Review**
- End-to-end check, edge cases (no data, JP-only names)
- Retro: Go vs. C# — write this down, it's a great interview answer
- **Both projects done. This is the last day networking stays paused.**

---

## Week 3 — July 15–21: Project 3

You said you'll land on the idea closer to the time — good call, no reason to lock it in now. When you do, drop it in and I'll fill this week out properly (data model day, core feature day, integration day, polish day — same shape as the other two). A few things to decide once you pick it:
- What gap does it fill? (different language/stack than C#/.NET and Go? A different domain than sports-data or search?)
- Does it need a backend, or can it be simpler (CLI, script, extension) to keep the timeline realistic given it's compressed into one week?

**Networking resumes this week, lightly:**
- Daily 20–30 min: 2–3 connections, comment on posts — no public project posts yet, save that for when all 3 are live
- 1–2 low-key applications if a role is a genuinely good fit already

### Tue July 21 — Sprint Review
- Project 3 working end-to-end?
- Retro + prep for launch week

---

## Week 4 — July 22–29: Package, Launch, Present

**Theme:** This is the week the pause on networking pays off — you launch with 3 finished things to point at, not a half-built profile.

**Wed July 22 — Project 3 Packaging**
- README, demo/screenshots, deployment or release build
- Networking: 2–3 connections

**Thu July 23 — Cross-Project Polish**
- Bug fixes across all 3, loading/empty/error states, caching if needed
- Networking: light

**Fri July 24 — The Launch**
- LinkedIn About section + headline overhaul, pin all 3 projects with links
- Resume update with full stack (C#/.NET, Go, [Project 3 stack], PostgreSQL, Docker, React)
- **Write and post the LinkedIn post** — now it lands with substance behind it
- Networking: this is the day it goes public

**Sat July 25 — Interview Prep: Your Projects**
- Write the "story" for each project — why, hard decisions, tradeoffs **[use your NOTES.md explain-backs as raw material]**
- Practice explaining anomaly detection, Go concurrency, and Project 3's core logic out loud

**Sun July 26 — Interview Prep: Fundamentals**
- SQL: top-5-upsets query from memory
- Docker: explain docker-compose.yml line by line, unaided
- Git: walk your own commit history
- 3–5 LeetCode (medium)

**Mon July 27 — Stretch Goals (pick any)**
- CI/CD with GitHub Actions
- Blog post about one project
- One open-source contribution
- Networking: 2–3 applications, follow up on any replies

**Tue July 28 — Final Review**
- All 3 projects deployed/packaged and documented?
- GitHub profile professional, LinkedIn live and updated?
- Can you confidently talk about every technology across all 3 projects?
- **You're done. Start applying in earnest.**

---

## Success Metrics (v3)

By July 28:

**Build:**
- [ ] 3 pinned GitHub repos with clean READMEs and live demos/downloads
- [ ] ~28 days of GitHub contribution history
- [ ] Working knowledge of C#/.NET, Go, [Project 3 stack], PostgreSQL, Docker, React
- [ ] NOTES.md per project — your interview cheat sheets
- [ ] ~28 LeetCode problems solved

**Network/Launch:**
- [ ] LinkedIn live with all 3 projects, posted once you had something real to show
- [ ] Some networking groundwork from week 3 already in motion before launch
- [ ] Applications going out from week 4 onward

---

## Notes
- **Why the pause made sense:** networking before you have proof is just noise for both you and the people you'd reach out to. Waiting until week 3–4 means every message and post lands with something concrete behind it.
- **The explain-back habit still matters most now**, since two projects got compressed — make sure "faster" didn't mean "shallower." If you can't explain a piece of AI-drafted code in your own words, that's the flag to slow down on that piece specifically.
- **If Week 1 compression feels too tight once you're in it:** better to let Esports Tracker bleed a day into Week 2 than ship something you can't explain. Sake Search can absorb a day of slack since it was already realistically paced.
- **When you pick Project 3**, send it over and I'll build out the week-3 daily breakdown to match.
