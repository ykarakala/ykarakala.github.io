# Portfolio Website Build Context & Prompt History

This document captures the full history of prompts and decisions used to build Yugandhar Reddy's portfolio website, so the process can be replicated or continued.

---

## Phase 1: Initial Site Creation

**Prompt:** Create a website with "About", "Experience", "Skills", "Contact" sections similar to the local reference site.

- Built single-page `index.html` with dark theme, sticky nav, smooth scroll, hero section, About with bio + metric cards, Experience timeline, Skills grid, Contact with form + info cards, and footer.
- Used inline CSS with CSS variables for theming.

**Prompt:** Scale the first section (hero) by 40%.

- Reduced hero `min-height` from 100vh to 60vh, scaled down avatar, fonts, and padding by ~40%.

**Prompt:** Add dark/light clickable toggle, default to light mode.

- Added light mode CSS variables as `:root` default, dark mode under `[data-theme="dark"]`.
- Added theme toggle button in nav with localStorage persistence.
- Updated hero gradient and muted color references to use CSS variables.

**Prompt:** Use `ykreddy.jpg` as profile picture.

- Replaced the "YR" text avatar with an `<img>` tag referencing `ykreddy.jpg`.

---

## Phase 2: Design System Migration (pranav_html)

**Prompt:** Use `/Users/ykreddy/pranav_html/styles.css` as the design system.

- Copied `styles.css` from `pranav_html/` into `GitHub_web/`.
- Rebuilt `index.html` to use the external stylesheet with the pranav design system: indigo/blue gradient hero, glassmorphism profile card, card hover animations, contact tiles, pill-style skill tags, nav scroll color change, and floating + nav theme toggles.

**Prompt:** Match contacts tile to the pranav contact.html design.

- Read `pranav_html/contact.html` and adopted the centered `contact-card` tile layout (icon, title, link).

---

## Phase 3: Content & Color Customization

**Prompt:** Update phone to 408-569-1265, email to yugreddy@yahoo.com.

- Updated contact info in both the contact cards.

**Prompt:** Update About paragraph with expanded Aurora MySQL description (PQ, PE, left-shift quality, version currency, etc.).

- Replaced the third About paragraph with detailed current role description.

**Prompt:** Change "the larger data at the scale" to "the larger data at scale", then to "the larger data sets at the scale".

- Text corrections applied.

**Prompt:** Change hero background to "aurora colors".

- Updated hero gradient in `styles.css` to: `#0b3d2e → #0d6b58 → #1a8a7a → #2d6b8a → #4a3f8a` (green-teal-blue-purple aurora borealis).

**Prompt:** Change entire site color palette to match hero.

- Updated `:root` and `[data-theme="dark"]` CSS variables: primary `#1a8a7a`, primary-dark `#0d6b58`, secondary `#2d6b8a`, accent `#4a3f8a`.
- Updated nav.scrolled gradient, page-header gradient, button shadows, and card-icon shadows to use teal/aurora colors.
- Removed all hardcoded indigo (`#6366f1`) references.

**Prompt:** Add "Storage" and "File Systems" tech tags, change "Aurora MySQL" to "AWS Aurora".

- Updated hero tech tags and subtitle.

**Prompt:** Reduce hero empty space (remove min-height: 70vh → auto).

---

## Phase 4: Featured Launches Section

**Prompt:** Enrich portfolio with Aurora Serverless v2 blog post data.

- Fetched https://aws.amazon.com/blogs/aws/amazon-aurora-serverless-v2-is-generally-available-instant-scaling-for-demanding-workloads/
- Updated experience bullet with GA 2022 details.
- Created "Featured Launches & Media" section with blog link card.

**Prompt:** Link YouTube video https://www.youtube.com/watch?v=xKFA6PJgp0o

- Added embedded YouTube iframe in the launches section.

**Prompt:** Link YouTube video https://www.youtube.com/watch?v=Kap0I5g1AbI

- Added second embedded YouTube iframe (Deep Dive).

**Prompt:** Combine all Aurora Serverless v2 items into one card.

- Merged blog post card + two video cards into a single card with side-by-side video embeds.

**Prompt:** Add PQv2 launch card with documentation link.

- Added Aurora MySQL Parallel Query v2 card.

**Prompt:** Add Parallel Export launch card.

- Added Parallel Export card with docs link.

**Prompt:** Add Aurora MySQL Fast Restart launch card.

- Added Fast Restart card with AWS announcement link.

**Prompt:** Add Aurora MySQL & Amazon Bedrock integration card.

- Added Bedrock SQL integration card with blog link.

**Prompt:** Update subtitle to "Key AWS product and service launches and public references from my team's deliverables".

---

## Phase 5: Worklog Data Enrichment

**Prompt:** Use KYR 2022-2023 worklog data to enrich About, metrics, and experience.

- Enriched About with NetApp background (21 years, 50+ staff HCI, 160+ CPE org, $6B business).
- Expanded metrics from 4 to 8 tiles: 20+ years, 3,000+ CRs, 40% crash reduction, 24x faster restarts, $6M+ savings, 28% storage CapEx, 15+ escalations, 56% ops reduction.
- Expanded AWS experience from 10 to 17+ bullets incorporating: Caspian delivery, AMS 3.05.0, Tidal/ZeroETL GA, mini-COE framework, LTTR/CR lifecycle systems, JIRA migration, PageWriter optimization, follow-the-sun on-call.

---

## Phase 6: Content Refinements

**Prompt:** Remove all customer names, replace with "Fortune-10 enterprises".

**Prompt:** Remove "(GA 2022)" from experience bullet.

**Prompt:** Various text replacements:
- "Aurora MySQL" references standardized
- "Handspring" removed from all references
- "100% Yugen pass rate" → "100% MySQL Test Run pass rate"
- "CIT" → "Customer Tickets"
- "ZeroETL" standardized as one word (was "Zero ETL" in some places)
- "100x" → "100-300x based on the data set"
- Multiple grammar and tense fixes

**Prompt:** Rewrite fleet stability bullet to emphasize ownership.

- "Owned fleet stability post Serverless v2 GA — drove three hardening patches, cut engine crashes 40%..."

**Prompt:** Rewrite PageWriter bullet to emphasize operational excellence.

- "Tackled long-standing PageWriter memory overuse — sponsored optimization team, reduced storage node memory and CapEx by 28%"

**Prompt:** Rewrite customer escalations bullet.

- "Drove 100+ customer escalations to resolution including 15+ Fortune-10 enterprises — relentless customer obsession under pressure"

**Prompt:** Make all AWS experience bullets sharper and shorter.

- Tightened every bullet to lead with strong action verbs, front-loaded metrics, removed filler.

**Prompt:** Rebrand "Senior Director, HCI Engineering" → "Senior Director, HCI/SRE Engineering".

---

## Phase 7: Contact Section & Downloads

**Prompt:** Link `YUGANDHAR REDDYW.pdf` as Resume download tile in contact section.

**Prompt:** Link `KYR_timeline_profile.pdf` as "Profile" download tile.

**Prompt:** Remove Location tile, fit all contact cards in one row (5 columns).

**Prompt:** Rename tiles: "Download (PDF)" → "Resume (PDF)" / "Profile (PDF)".

---

## Phase 8: Mobile Responsiveness

**Prompt:** Make site auto-scale for all devices.

- Added comprehensive responsive CSS at 1024px, 768px, and 480px breakpoints.
- Added hamburger menu (☰/✕) for mobile nav.
- Hero stacks vertically on mobile, profile photo moves above text.
- Contact cards stack to single column on phones.
- Metrics grid adapts: 4 → 2 columns.
- CTA buttons stack vertically on small phones.
- All text, padding, tags scale down progressively.

---

## Phase 9: Cleanup

**Prompt:** Remove unnecessary files from workspace.

- Deleted: worklog HTML, PowerPoint, TIFFs, duplicate PDFs, reference HTML, duplicate JPG.
- Kept: `index.html`, `styles.css`, `YKREDDY.jpg`, `YUGANDHAR REDDYW.pdf`, `KYR_timeline_profile.pdf`, `README.md`.

**Prompt:** Remove floating theme toggle (bottom-right), keep nav toggle only.

**Prompt:** Populate README.md with project description.

---

## File Structure (Final)

```
GitHub_web/
├── index.html                  # Main portfolio page
├── styles.css                  # Design system (aurora theme, light/dark)
├── YKREDDY.jpg                 # Profile photo
├── YUGANDHAR REDDYW.pdf        # Downloadable resume
├── KYR_timeline_profile.pdf    # Downloadable experience timeline
├── README.md                   # Project description
└── context.md                  # This file — build history
```

---

## Key Design Decisions

1. **Single-page app** — all sections on one page with smooth scroll nav
2. **Aurora color palette** — green/teal/blue/purple gradient matching AWS Aurora branding
3. **External CSS** — shared `styles.css` design system (originally from pranav_html)
4. **Light mode default** — dark mode via `[data-theme="dark"]` with localStorage persistence
5. **Hamburger nav on mobile** — collapses to vertical menu below 768px
6. **Recruiter-optimized** — strong action verbs, front-loaded metrics, highlighted AWS card with accent border
7. **Featured Launches** — embedded YouTube videos + AWS blog/doc links for credibility
8. **Downloadable assets** — Resume and Profile PDFs linked in contact section

---

## Workspace Context

**Workspace path:** `/Users/ykreddy/Desktop/GitHub_web`
**OS:** macOS (darwin, bash shell)
**Dev server:** Live Server (VS Code) at `http://127.0.0.1:5501/index.html`

### Multi-root workspace (during build)
- `GitHub_web/` — the portfolio site (primary)
- `pranav_html/` — reference design system (Pranav Reddy's portfolio, used as CSS source)

### Reference files used during build (no longer in workspace)
- `pranav_html/styles.css` — copied as the base design system
- `pranav_html/index.html` — referenced for hero layout, nav structure, card styles
- `pranav_html/contact.html` — referenced for contact tile design
- `GitHub_web/reference_index.html` — copy of pranav's index (deleted during cleanup)

---

## Data Sources Used

### Resume / Profile Data
- Resume PDF content (pasted as text in chat) — Yugandhar Reddy's full resume with 20+ years experience at AWS and NetApp
- `KYR_timeline_profile.pdf` — experience timeline document
- `YUGANDHAR REDDYW.pdf` — formal resume

### AWS Blog Post (fetched)
- **URL:** https://aws.amazon.com/blogs/aws/amazon-aurora-serverless-v2-is-generally-available-instant-scaling-for-demanding-workloads/
- **Used for:** Aurora Serverless v2 GA details — 0.5-128 ACU scaling, read replicas, Multi-AZ, Global Database, 90% cost savings, in-place millisecond scaling, conservative scale-down

### KYR 2022-2023 Worklog (pasted as HTML in chat)
- **Source:** Internal Quip document `quip-amazon.com/aLa0AKHJxJcq/KYR-2022-2023-worklog`
- **Key projects extracted:**
  - Caspian (Serverless v2) delivery — Apr 2022
  - ASv1 operational excellence — 50 tickets/month reduction
  - ASv2 scale-up/down ACT refactoring and Minion SOP automation
  - AMS 3.02.1 hardening — 40% crash reduction
  - Zero Downtime roadmap, feature completion, test gaps
  - MySQL 8.0 hardening — automated perf benchmarks, chaos testing, stress frameworks
  - Summer intern program
  - 15+ customer escalations (Bitpanda, SP+, CDO, Mobly, Genesys, Sterling, Affirm, T-Mobile, etc.)
  - Mini-COE framework — 6 cross-functional gaps identified
  - AMS Jira MVP workflows
  - VC 3.05 strategy — 3,000+ CRs, predictable integration cycles
  - Tidal (ZeroETL) GA delivery
  - Fast Restart (Handspring) — P98.5 <5s, P99 <10s
  - PageWriter memory optimization — 28% CapEx reduction
  - LTTR data system, CR lifecycle system, issue exposure system, CIT metrics system
  - SIM-to-JIRA migration strategy
  - Follow-the-sun on-call model
  - AMS 2024 planning exercise

### YouTube Videos (embedded)
- **Overview:** https://www.youtube.com/watch?v=xKFA6PJgp0o
- **Deep Dive:** https://www.youtube.com/watch?v=Kap0I5g1AbI

### AWS Documentation Links (in launches section)
- PQv2: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-mysql-parallel-query.html
- Parallel Export: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-export-snapshot.parallel.html
- Fast Restart: https://aws.amazon.com/about-aws/whats-new/2023/10/amazon-aurora-mysql-reduce-database-restart-time/
- Bedrock Integration: https://aws.amazon.com/blogs/database/integrate-amazon-aurora-mysql-and-amazon-bedrock-using-sql/

---

## Profile Information (for reference)

- **Name:** Yugandhar Reddy
- **Current Role:** Engineering Leader, Aurora MySQL — Amazon Web Services (AWS)
- **Location:** San Francisco Bay Area / Palo Alto, CA
- **Start at AWS:** Dec 2021
- **Prior:** 21 years at NetApp (Sr. Director HCI/SRE Engineering, Director CPE, multiple positions)
- **Education:** MS Electrical & Computer Engineering (Wichita State), BS Electrical & Electronics Engineering (Osmania University)
- **Email:** yugreddy@yahoo.com
- **Phone:** 408-569-1265
- **LinkedIn:** https://www.linkedin.com/in/yugreddy
- **Profile photo:** `YKREDDY.jpg`

---

## CSS Theme Variables (current)

### Light Mode (default)
```css
--primary: #1a8a7a;
--primary-dark: #0d6b58;
--secondary: #2d6b8a;
--accent: #4a3f8a;
--bg-body: #ffffff;
--bg-card: #ffffff;
--bg-light: #f0faf8;
--footer-bg: #0b3d2e;
```

### Dark Mode
```css
--bg-body: #0a1f1a;
--bg-card: #0f2b26;
--bg-light: #0f2b26;
--footer-bg: #061510;
```

### Hero Gradient
```css
background: linear-gradient(135deg, #0b3d2e 0%, #0d6b58 30%, #1a8a7a 50%, #2d6b8a 70%, #4a3f8a 100%);
```

---

## Responsive Breakpoints

| Breakpoint | Target | Key Changes |
|-----------|--------|-------------|
| ≤1024px | Tablets/small laptops | Hero stacks, metrics 4→2 cols, contact 5→3 cols |
| ≤768px | Tablets portrait/large phones | Hamburger nav, all grids single column, contact stacks |
| ≤480px | Phones | Smaller fonts, CTA buttons stack, compact metrics/cards |

---

## How to Continue Building

1. Open workspace at `/Users/ykreddy/Desktop/GitHub_web` in VS Code
2. Use Live Server to preview at `http://127.0.0.1:5501/index.html`
3. Reference this `context.md` for all past decisions and data sources
4. Key files: `index.html` (content), `styles.css` (design system)
5. To deploy: `git init && git add . && git commit -m "msg" && git push` to GitHub, enable GitHub Pages
