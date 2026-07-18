# Search Queries for Job Scraper

<!-- Profile: David Andres Cedeño Ortiz — Unity / Node.js / Backend / GHL Automation -->
<!-- Location: San José de Cúcuta, Colombia — Remote or local Cúcuta only -->
<!-- Salary minimum: $1,000 USD/month -->

## Search Sites

Primary:
- **linkedin.com/jobs** — LinkedIn (filter: Remote / Colombia / Worldwide)
- **indeed.com** — Indeed (filter: Remote / "Cúcuta" / "Colombia")
- **Facebook groups** — Colombian dev communities (e.g. "Desarrolladores Colombia", "Unity Developers Colombia", "Node.js Colombia", "Remote Jobs Colombia")

Secondary (company career pages via Google):
- `site:linkedin.com/jobs "Unity Developer" remote`
- `site:indeed.com "Node.js Developer" remote Colombia`

## Query Categories

### Priority 1: Game Development / Unity

Strongest match — 6+ years building 2D/3D games.

```
site:linkedin.com/jobs "Unity Developer" remote
site:linkedin.com/jobs "Game Developer" Unity remote
site:indeed.com "Unity Developer" remote
site:indeed.com "Game Developer" "Node.js" remote
"Unity Developer" remote Colombia
"Game Developer" Unity C# remote
```

### Priority 2: Backend / Node.js

Strong match — production Node.js, REST APIs, WebSockets across multiple roles.

```
site:linkedin.com/jobs "Node.js Developer" remote
site:linkedin.com/jobs "Backend Developer" "Node.js" remote
site:indeed.com "Node.js Developer" remote Colombia
site:indeed.com "Backend Developer" "WebSockets" remote
"Node.js Developer" remote "$" OR "USD"
"Backend Developer" Node.js REST APIs remote
```

### Priority 3: Full Stack / Software Engineer

Broader net — leverages the cross-layer breadth (game + backend + web).

```
site:linkedin.com/jobs "Full Stack Developer" "Node.js" remote
site:linkedin.com/jobs "Software Engineer" "Unity" OR "Node.js" remote Colombia
site:indeed.com "Full Stack Engineer" remote Colombia
"Software Engineer" "Node.js" OR "Unity" remote Colombia
```

### Priority 4: Adjacent — Automation / GHL / Integration

Covers the Bulldog Studio work — growing market for GHL specialists.

```
site:linkedin.com/jobs "Go High Level" developer remote
site:linkedin.com/jobs "Automation Developer" "GHL" OR "Go High Level" remote
site:indeed.com "GHL Developer" remote
"Go High Level" developer remote
"Automation Engineer" "API" "webhooks" remote Colombia
```

## Location Filter

When evaluating results:
- **Ideal:** Remote (worldwide or Latin America)
- **Acceptable:** Presencial in San José de Cúcuta, Norte de Santander
- **Borderline:** Hybrid Cúcuta (flag for review)
- **Too far:** Presencial in another city requiring relocation (hard reject)

## Salary Filter

Flag any posting where the stated salary or rate is below $1,000 USD/month equivalent. If no salary is listed, include the posting but note "salary unknown — verify before applying."

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If posting date cannot be determined, include but flag as "date unknown."

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
