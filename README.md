# 4-Week Sprint Plan — July 2026

**Goal:** Two portfolio-ready projects + stronger fundamentals → more hireable in one month.

**Projects:**
1. **Esports Odds & Integrity Tracker** — .NET/C#, PostgreSQL, React, Docker (Web app)
2. **Sake Search** — Go terminal app for Japanese alcohol discovery with anime references & SG availability

**Schedule:** Wed → Mon = build days. Tuesday = review & plan next sprint.

---

## Daily Recurring Tasks (every day, before project work)

| Task | Time |
|---|---|
| 1 LeetCode problem (easy/medium, arrays/hashmaps/strings) | 20 min |
| Git practice: use branches, write real commit messages, open PRs to your own main | Baked into project work |
| Push something to GitHub (code, docs, anything) | Non-negotiable |

---

## Week 1 — July 1–8: Foundation + Esports Backend

**Theme:** Set up your dev environment, learn .NET basics, get the API skeleton running.

### Wednesday July 1 — Environment Day
- Install .NET SDK, PostgreSQL, Docker Desktop, Rider or VS Code with C# extension
- Create GitHub repos for both projects (with .gitignore, LICENSE, empty README)
- Pin both repos on your GitHub profile
- Scaffold a new ASP.NET Web API project (dotnet new webapi)
- Make your first real commit with a message like "feat: scaffold ASP.NET API project"

### Thursday July 2 — Data Model Day
- Design the database schema: Teams, Matches, Odds, Markets
- Set up Entity Framework Core with PostgreSQL (Npgsql)
- Write and run your first migration
- SQL practice: write raw queries for your schema (joins across teams/matches)

### Friday July 3 — First Endpoints
- Build CRUD endpoints for Teams and Matches
- Proper HTTP status codes (201 on create, 404 on not found, 400 on bad input)
- Input validation and error handling
- Test with curl or Postman — screenshot results for your README

### Saturday July 4 — External Data
- Research esports APIs (PandaScore, Riot API, OpenDota) — pick one, get an API key
- Build a background service or scheduled job to pull live match data
- Map external API response to your data model
- Store fetched data in PostgreSQL

### Sunday July 5 — Odds Integration
- Research prediction market / odds APIs (Polymarket, public bookmaker APIs)
- Build a service to pull odds data and associate it with matches
- Create an endpoint: GET /matches/{id}/odds — returns match info + crowd sentiment
- Start writing the "What is this?" section of your README

### Monday July 6 — Anomaly Detection MVP
- Build the match anomaly logic: flag matches where odds shifted > X% in the last Y hours before the result
- Create endpoint: GET /matches/anomalies — returns flagged matches with context
- Write at least 2 unit tests for your anomaly detection logic
- Update README with API documentation

### Tuesday July 7 — Sprint Review 1
- Review: do all endpoints work? Is the code committed and pushed?
- Retrospective: what took longer than expected? What do you need to learn?
- Plan adjustments for Week 2
- Write a short "Week 1" section in your README (what you built, what you learned)

---

## Week 2 — July 8–15: Esports Frontend + Deploy

**Theme:** Make it visual, Dockerize it, ship it live.

### Wednesday July 8 — Frontend Scaffold
- Set up React app (Vite + TypeScript recommended)
- Build the layout: navbar, match list page, match detail page
- Fetch data from your API and display a list of matches
- If new to React: spend first 2 hours on a crash course, then build

### Thursday July 9 — Data Visualization
- Add a chart library (Recharts or Chart.js)
- Match detail page: show odds movement over time as a line chart
- Add the "crowd confidence meter" — a simple visual indicator
- Color-code upsets vs expected results

### Friday July 10 — Anomaly Dashboard
- Build an anomaly dashboard page showing flagged matches
- Visual indicators for suspicion level (odds swing magnitude)
- Add filtering: by game, by date range, by suspicion threshold
- Polish the UI — it doesn't need to be beautiful, but it needs to be clear

### Saturday July 11 — Docker Day
- Write a Dockerfile for the .NET API
- Write a Dockerfile for the React frontend
- Create docker-compose.yml: API + PostgreSQL + frontend
- Verify the whole stack runs with one `docker-compose up`

### Sunday July 12 — Deploy
- Deploy to a free host (Railway, Render, or Azure free tier)
- Set up environment variables properly (no secrets in code)
- Verify it works on a public URL
- Add the live link to your README and GitHub repo description

### Monday July 13 — Polish & Document
- README overhaul: project description, screenshots, tech stack, how to run locally, how to run with Docker, API docs, live demo link
- Add a "Lessons Learned" section
- Clean up any messy code, add comments where logic is complex
- Make sure commit history tells a coherent story

### Tuesday July 14 — Sprint Review 2
- Review: is Project 1 fully deployed and documented?
- Can you demo it to someone and explain every technical decision?
- Retrospective: what went well, what would you do differently?
- Mental shift: you're switching languages tomorrow

---

## Week 3 — July 15–22: Sake Search (Go)

**Theme:** Learn Go by building. Ship a polished terminal app.

### Wednesday July 15 — Go Day 1
- Install Go, set up your editor (VS Code + Go extension or GoLand)
- Go through "A Tour of Go" (2-3 hours — focus on structs, interfaces, goroutines, error handling)
- Write a "hello world" CLI that accepts a flag and prints formatted output
- Commit: "feat: initial Go CLI scaffold"

### Thursday July 16 — API Research & Client
- Research public APIs for alcohol/sake data (Untappd, sake databases, liquor store APIs in SG)
- If no clean API exists: plan a local JSON dataset you'll curate manually as MVP
- Build an HTTP client in Go to fetch from your chosen data source
- Parse JSON response into Go structs

### Friday July 17 — Core Search
- Implement search: user types a drink name (romaji, English, or Japanese)
- Return: name (JP + EN), type, ABV, tasting notes, price range
- Handle partial matches and fuzzy search
- Add a Bubble Tea TUI (terminal UI) for a polished interactive experience

### Saturday July 18 — Anime Reference Mode
- Build a local dataset: map drinks to anime appearances (Botan Kamiina, Bartender, Isekai Izakaya, etc.)
- Command: `sakesearch --anime "botan kamiina"` → lists drinks featured in that show
- Command: `sakesearch --episode "botan kamiina s1e3"` → specific episode references
- Reverse lookup: `sakesearch "junmai daiginjo" --appearances` → which anime featured it

### Sunday July 19 — Singapore Availability
- Research: where is Japanese alcohol sold in SG? (Don Don Donki, liquor shops, online stores)
- Build a module that checks availability/pricing from public sources
- Output: "Available at Don Don Donki (Orchard) — ~$45 SGD"
- Add currency formatting and location-aware output

### Monday July 20 — Translation & Polish
- Integrate a translation layer for Japanese → English drink names and descriptions
- Add `--lang jp` flag to toggle Japanese output
- Write comprehensive tests for search, translation, and availability logic
- Build the binary: `go build` → test the .exe works standalone

### Tuesday July 21 — Sprint Review 3
- Review: does the app work end-to-end?
- Test edge cases: drinks with no data, no availability, Japanese-only names
- Retrospective: how does Go feel compared to Java and C#?
- Start thinking about packaging and distribution

---

## Week 4 — July 22–29: Package, Polish, Present

**Theme:** Make everything portfolio-ready. You're not building new features — you're shipping.

### Wednesday July 22 — Sake Search Packaging
- Create a GitHub Release with pre-built binaries (Linux, macOS, Windows)
- Write a killer README: what it does, GIF/screenshot of it in action, install instructions, usage examples
- Add a "Built With" section and architecture overview
- Make the repo visually appealing (good formatting, maybe a logo/banner)

### Thursday July 23 — Esports Tracker Final Polish
- Fix any bugs from the deployed version
- Add one more visual touch (loading states, empty states, error states)
- Performance check: are API responses fast? Add caching if needed
- Final README review — would a stranger understand this in 60 seconds?

### Friday July 24 — LinkedIn & Portfolio Day
- Update LinkedIn headline and About section
- Add both projects as LinkedIn "Projects" with descriptions and links
- Write a short LinkedIn post about what you built and learned this month
- Update your resume with the new tech stack (C#/.NET, Go, PostgreSQL, Docker, React)

### Saturday July 25 — Interview Prep: Your Projects
- Write down the "story" for each project: why you built it, hard decisions, tradeoffs
- Practice explaining your anomaly detection logic (whiteboard-style)
- Practice explaining Go concurrency choices in Sake Search
- Prepare for "what would you add next?" questions

### Sunday July 26 — Interview Prep: Fundamentals
- Review your SQL: can you write a query to find the top 5 most upset matches?
- Review Docker: can you explain your docker-compose.yml line by line?
- Review Git: can you walk through your commit history and explain your workflow?
- Do 3-5 LeetCode problems (medium) as a final push

### Monday July 27 — Stretch Goals (pick any)
- Add CI/CD with GitHub Actions (even a simple lint + test pipeline)
- Write a blog post about building one of the projects (dev.to or hashnode)
- Contribute to an open-source project (even a small docs fix)
- Set up the X / Instagram page for one of your projects

### Tuesday July 28 — Final Sprint Review
- Both projects deployed/packaged and documented?
- GitHub profile looks professional? (bio, pinned repos, green graph)
- LinkedIn updated?
- Can you confidently talk about every technology you used?
- **You're done. Start applying.**

---

## Success Metrics

By July 28, you should have:

- [ ] 2 pinned GitHub repos with clean READMEs and live demos/downloads
- [ ] ~28 days of GitHub contribution history
- [ ] Working knowledge of C#/.NET, Go, PostgreSQL, Docker, React
- [ ] A deployed web app anyone can visit
- [ ] A downloadable Go binary anyone can run
- [ ] Updated LinkedIn with project links
- [ ] ~28 LeetCode problems solved
- [ ] Confidence to talk about your projects in an interview

---

## Notes

- **If you fall behind:** Cut scope on the current task, don't skip days. A working feature with rough edges beats an unfinished polished one.
- **If you get stuck:** Timebox to 30 minutes, then ask for help (Stack Overflow, Discord, or come back here).
- **If you finish early:** Add tests, add CI/CD, write a blog post, or start the next week early.
- **The daily LeetCode is non-negotiable.** 20 minutes. Set a timer. Stop when it rings even if you didn't solve it — read the solution and move on.
