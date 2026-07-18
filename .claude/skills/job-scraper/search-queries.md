# Search Queries for Job Scraper

<!-- Profile: David Andres Cedeño Ortiz — Unity / Node.js / Backend / GHL Automation -->
<!-- Location: San José de Cúcuta, Colombia — candidate works remotely, so remote roles worldwide are in scope, not just Colombia/Latin America; local Cúcuta presencial also acceptable -->
<!-- Salary minimum: $1,000 USD/month -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

## Search Sites

Primary (also covered by `linkedin-search` CLI; scaffold more with `/add-portal`):
- **linkedin.com/jobs** — LinkedIn (filter: Remote worldwide, or "Cúcuta" for local presencial)
- **indeed.com** — Indeed (filter: Remote worldwide, or "Cúcuta" for local presencial)
- **Facebook groups** — Colombian dev communities (e.g. "Desarrolladores Colombia", "Unity Developers Colombia", "Node.js Colombia", "Remote Jobs Colombia") plus broader remote-work groups, since remote roles aren't limited to Colombia-based companies

Secondary (company career pages via Google):
- `site:linkedin.com/jobs "Unity Developer" remote`
- `site:indeed.com "Node.js Developer" remote`

## Query Categories

### Priority 1: Game Development / Unity

Strongest match — 6+ years building 2D/3D games.

```
site:linkedin.com/jobs "Unity Developer" remote
site:linkedin.com/jobs "Game Developer" Unity remote
site:indeed.com "Unity Developer" remote
site:indeed.com "Game Developer" "Node.js" remote
"Unity Developer" remote
"Game Developer" Unity C# remote
```

### Priority 2: Backend / Node.js

Strong match — production Node.js, REST APIs, WebSockets across multiple roles.

```
site:linkedin.com/jobs "Node.js Developer" remote
site:linkedin.com/jobs "Backend Developer" "Node.js" remote
site:indeed.com "Node.js Developer" remote
site:indeed.com "Backend Developer" "WebSockets" remote
"Node.js Developer" remote "$" OR "USD"
"Backend Developer" Node.js REST APIs remote
```

### Priority 3: Full Stack / Software Engineer

Broader net — leverages the cross-layer breadth (game + backend + web).

```
site:linkedin.com/jobs "Full Stack Developer" "Node.js" remote
site:linkedin.com/jobs "Software Engineer" "Unity" OR "Node.js" remote
site:indeed.com "Full Stack Engineer" remote
"Software Engineer" "Node.js" OR "Unity" remote
```

### Priority 4: Adjacent — Automation / GHL / Integration

Covers the Bulldog Studio work — growing market for GHL specialists.

```
site:linkedin.com/jobs "Go High Level" developer remote
site:linkedin.com/jobs "Automation Developer" "GHL" OR "Go High Level" remote
site:indeed.com "GHL Developer" remote
"Go High Level" developer remote
"Automation Engineer" "API" "webhooks" remote
```

## Location Filter

When evaluating results:
- **Ideal:** Remote, worldwide — the candidate works remotely, so this is not limited to Colombia or Latin America
- **Acceptable:** Presencial in San José de Cúcuta, Norte de Santander
- **Borderline:** Hybrid Cúcuta (flag for review)
- **Too far:** Presencial in another city requiring relocation (hard reject) — this only applies to on-site/hybrid roles that require physically moving; fully remote roles are never rejected for the employer's country/city

## Salary Filter

Flag any posting where the stated salary or rate is below $1,000 USD/month equivalent. If no salary is listed, include the posting but note "salary unknown — verify before applying."

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If posting date cannot be determined, include but flag as "date unknown."

## Language Filter

Exclude postings whose title and description are written entirely in English, by default — even when the posting does not state an English-language requirement. A vacancy published in English signals the recruiter will expect English fluency in practice (screening calls, interviews, day-to-day communication), and the candidate's English is at a basic/intermediate level, so this is treated as a deal-breaker on par with the location filter, not a soft preference.

**Exception:** If the posting's own text explicitly states that English is *not* required, or that only basic/elementary English is required (e.g. "no English required," "basic English," "English not necessary," "conversational English is enough"), the posting passes the filter despite being written in English — the explicit statement overrides the inference from the posting's language. Note this exception explicitly when presenting the job (e.g. "posting is in English, but explicitly states basic English is sufficient").

Postings in Spanish (or bilingual, with a genuine Spanish-first version) pass this filter regardless of the underlying company's home country. Record excluded postings in `seen_jobs.json` as `status: "skipped"` rather than dropping them silently, so they don't get re-fetched on the next run.

## Suggested Role Types (Not in Priority Queries — Consider Adding)

Based on the profile, these adjacent titles also fit and are worth monitoring:
- **"Integration Developer"** — GHL + APIs + webhooks experience maps directly
- **"Technical Consultant" (GHL/CRM)** — Bulldog Studio work demonstrates client-facing delivery
- **"Real-Time Systems Developer"** — WebSockets + game networking experience is a differentiator
- Run `/scrape integration developer` or `/scrape GHL consultant` to test these lanes

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and generate 2-3 custom queries for that focus. For example:
- `/scrape unity` → Priority 1 queries + custom Unity-specific terms
- `/scrape node` → Priority 2 queries + "Express", "REST", "WebSockets" variants
- `/scrape automation` → Priority 4 queries + GHL-specific terms
