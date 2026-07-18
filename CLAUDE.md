# Job Application Assistant for [YOUR_NAME]

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for [YOUR_NAME], helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** David Andres Cedeño Ortiz (goes by Andres)
- **Location:** San José de Cúcuta, Norte de Santander, Colombia
- **Phone:** +573026534479
- **Email:** daviddaco1998@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/andres-ortiz-99a619202
- **Portfolio:** https://portfolio.andresodev.com/
- **GitHub:** https://github.com/daviddaco1
- **Languages:** Spanish (Native), English (Basic)
- **Status:** Currently employed at Bulldog Studio (Sep 2025 – present)
- **LinkedIn headline:** "Full Stack .NET Developer | Full Stack Engineer | C# | Node.js | REST APIs | Docker | Distributed Systems"

### Education
- **Técnico Medio en Informática** (2015–2019) - Universidad Nacional Experimental Politécnica "Antonio José de Sucre", Anaco, Venezuela

### Professional Experience
- **Go High Level Developer | Automatización – Workflows – APIs – SaaS – CRM** (Sep 2025 – Present) - **Bulldog Studio** (Cúcuta, Colombia)
  - Website and landing page development using Go High Level
  - Automated workflows, API integration, webhooks, CRM pipelines, lead generation systems
  - SaaS modules and functionalities within GHL; optimizing business processes
- **Game Developer 2D/3D | Backend Node.js | APIs & WebSockets | Security | Frontend** (Jun 2024 – Jun 2025) - **ThunderShark** (Cúcuta, Colombia)
  - 2D/3D games for mobile and desktop; Node.js backend with REST APIs and WebSockets
  - Databases, IT security, internal tools, and frontend for administrative panels
- **Junior Game Developer** (Nov 2023 – May 2024) - **Mega Cat Studios** (Cúcuta, Colombia)
  - 2D/3D mobile and desktop game development; UI/UX, gameplay mechanics, enemy AI
- **Game Developer | 2D/3D Mobile – UI/UX – API Integration** (Jun 2021 – Oct 2023) - **Coinary LTD** (Cúcuta, remote with international teams)
  - 2D/3D mobile games; API integration with external servers; real-time data management
- **Programmer | Web Development & Desktop Applications** (Jun 2018 – Jun 2020) - **INELECSI SL** (Anaco, Venezuela)
  - Corporate website development; desktop apps for internal processes
- **Programmer | Game Development | Administrative Apps | Blender 3D** (Jan 2015 – Jan 2018) - **Independent / Autónomo** (Anaco, Venezuela)
  - Video games, admin apps, Blender 3D modeling, backend solutions

### Technical Skills
- **Primary:** Unity (2D/3D), C#, Node.js, REST APIs, WebSockets, Go High Level
- **Secondary:** SQL, Docker, IT Security, Systems distribution, UI/UX, Photon, Nakama, APIs & Webhooks, Workflow automation
- **Domain:** Game development (mobile/desktop), backend systems, CRM/SaaS automation
- **Software:** Blender (basic), Go High Level, Unity, Photon, Nakama

### Certifications
- None found in documents

### Publications
- None found in documents

### Awards
- None found in documents

### Behavioral Profile
- **Pragmatic builder** - moves from idea to working product quickly; delivery-focused
- **Cross-layer thinker** - comfortable spanning game client, backend, and automation in the same project
- **Strengths:** Results-orientation, technical breadth, remote collaboration, rapid prototyping
- **Growth areas:** English proficiency (intermediate), formal credentials (compensated by experience)
- **Thrives in:** Fast-paced environments with clear goals and autonomy; cross-functional roles

### What Excites You
- Testing and integrating APIs or new functionalities — the exploration and "does this work?" phase
- Building systems where you can see the result working end-to-end
- Roles that keep multiple technical areas active (game dev, backend, automation)

### Target Sectors
- Game development studios (remote, international): Unity/2D/3D roles
- SaaS and tech companies: Node.js backend, API, and full-stack roles
- Marketing/automation agencies: GHL specialists and automation developers
- Startups: cross-functional software engineer roles

### Deal-breakers
- Purely on-site roles with no remote option (remote or hybrid in Cúcuta required)
- Roles below $1,000 USD/month
- Pure maintenance with no new development work

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
