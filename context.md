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

**Prompt:** Change hero background to "aurora colors".

- Updated hero gradient in `styles.css` to: `#0b3d2e → #0d6b58 → #1a8a7a → #2d6b8a → #4a3f8a` (green-teal-blue-purple aurora borealis).

**Prompt:** Change entire site color palette to match hero.

- Updated `:root` and `[data-theme="dark"]` CSS variables: primary `#1a8a7a`, primary-dark `#0d6b58`, secondary `#2d6b8a`, accent `#4a3f8a`.
- Removed all hardcoded indigo (`#6366f1`) references.

**Prompt:** Add "Storage" and "File Systems" tech tags, change "Aurora MySQL" to "AWS Aurora".

**Prompt:** Reduce hero empty space (remove min-height: 70vh → auto).

---

## Phase 4: Featured Launches Section

**Prompt:** Enrich portfolio with Aurora Serverless v2 blog post data.

- Fetched https://aws.amazon.com/blogs/aws/amazon-aurora-serverless-v2-is-generally-available-instant-scaling-for-demanding-workloads/
- Created "Featured Launches & Media" section.
- Embedded two YouTube videos side-by-side: Overview + Deep Dive.
- Added PQv2, Parallel Export, Fast Restart, and Bedrock integration cards.

**YouTube videos embedded:**
- Overview: https://www.youtube.com/watch?v=xKFA6PJgp0o
- Deep Dive: https://www.youtube.com/watch?v=Kap0I5g1AbI

---

## Phase 5: Worklog Data Enrichment

**Prompt:** Use KYR 2022-2023 worklog data to enrich About, metrics, and experience.

- Enriched About with NetApp background (21 years, 50+ staff HCI, 160+ CPE org, $6B business).
- Expanded metrics to 8 tiles: 20+ years, 3,000+ CRs, 40% crash reduction, 24x faster restarts, $6M+ savings, 28% storage CapEx, 15+ escalations, 56% ops reduction.
- Expanded AWS experience to 17+ bullets: Caspian/Serverless v2, AMS 3.05.0, ZeroETL GA, mini-COE framework, LTTR/CR lifecycle systems, JIRA migration, PageWriter, follow-the-sun on-call.

**Source:** Internal Quip document `quip-amazon.com/aLa0AKHJxJcq/KYR-2022-2023-worklog`

---

## Phase 6: Content Refinements

- Replaced all customer names with "Fortune-10 enterprises"
- Standardized "ZeroETL" (one word), "Aurora MySQL" references
- Removed "Handspring" references
- Tightened all AWS experience bullets — strong action verbs, front-loaded metrics
- Rebrand: "Senior Director, HCI Engineering" → "Senior Director, HCI/SRE Engineering"

---

## Phase 7: Contact Section & Downloads

- Linked `YUGANDHAR REDDYW.pdf` as Resume download tile
- Linked `KYR_timeline_profile.pdf` as Profile download tile
- Removed Location tile; 5-column contact grid
- Renamed tiles: "Resume (PDF)" / "Profile (PDF)"

---

## Phase 8: Mobile Responsiveness

- Comprehensive responsive CSS at 1024px, 768px, and 480px breakpoints
- Hamburger menu (☰/✕) for mobile nav
- Hero stacks vertically on mobile; profile photo moves above text
- Contact cards stack to single column on phones
- Metrics grid: 4 → 2 columns on mobile
- CTA buttons stack vertically on small phones

---

## Phase 9: Cleanup

- Deleted: worklog HTML, PowerPoint, TIFFs, duplicate PDFs, reference HTML, duplicate JPG
- Kept: `index.html`, `styles.css`, `YKREDDY.jpg`, `YUGANDHAR REDDYW.pdf`, `KYR_timeline_profile.pdf`, `README.md`
- Removed floating theme toggle (bottom-right); kept nav toggle only
- Populated README.md with project description

---

## Phase 10: Kiro Powers / Agentic AI-First Launch (May 2026)

**Sources fetched:**
- https://aws.amazon.com/about-aws/whats-new/2026/05/amazon-aurora-mysql-kiro-powers/
- https://aws.amazon.com/blogs/database/guide-your-amazon-aurora-mysql-migration-with-kiro-powers/

**Changes:**
- Added Featured Launch card: "🤖 Aurora MySQL + Kiro Powers — Agentic AI-First Database Development (2026)" with `--accent` left border
- Embedded demo video via HTML5 `<video>` tag at 60% width / max 640px (CloudFront MP4)
  - Video URL: https://d2908q01vomqb2.cloudfront.net/artifacts/DBSBlogs/DBBLOG-5632/power-edit.mp4?_=1
  - Label: "Watch the Kiro Powers in Action"
- Three links: What's New announcement, AWS Database Blog post, MCP Server docs
- Added experience bullet: Kiro Powers integration — natural language DB ops + guided RDS → Aurora MySQL migrations
- Updated About paragraph 3: "Agentic AI-First" framing
- Added "Agentic AI (MCP)" skill tag

**Key facts:**
- Announced May 27, 2026
- Bundles MCP server (data + control plane) + steering files + validation hooks
- Migration flow: Assess → Migrate → Promote → Switch, near-zero downtime in tens of seconds
- Available one-click from Kiro IDE and Kiro webpage, all Aurora MySQL AWS Regions
- MCP server docs: https://awslabs.github.io/mcp/servers/mysql-mcp-server

---

## Phase 11: Four New Deliverables (May–June 2026)

### 1. Aurora MySQL 8.4 GA (May 21, 2026)

**Source fetched:** https://aws.amazon.com/blogs/database/amazon-aurora-mysql-8-4-is-now-generally-available/

**Key facts:**
- First community MySQL LTS-aligned major version — closes a 5-year version currency gap (Aurora MySQL 8.0 equivalent shipped 2021)
- 6+ month cross-geo effort: Bangalore, Berlin, Toronto, Seattle, San Jose
- Multi-billion dollar revenue stream enabler for AWS
- Simplified versioning model: Aurora MySQL version number = community MySQL version number going forward
- TLS enforced by default; caching_sha2_password as default auth plugin; modern cipher suites only
- Automated upgrade prechecks (columnDefinition, authMethodUsage, auroraUnsupportedPluginsCheck, etc.)
- Upgrade paths: Blue/Green Deployments (recommended), in-place major version upgrade, snapshot restore, AWS DMS (certified at GA), Percona XtraBackup
- Available in all Aurora MySQL AWS Regions

**Changes:**
- Added Featured Launch card with blog link
- Added experience bullet: "Force-multiplied Aurora MySQL 8.4 GA..."
- Updated About paragraph 3 to reference 8.4 GA
- Added "MySQL Version Currency" to Database & Data skills

---

### 2. Agentic AI Operational Excellence Dashboard

**Internal URL:** aurora-ticket-analytics.beta.harmony.a2z.com (not linked — internal)

**Key facts:**
- Conceptualized, architected, and delivered by Yugandhar as innovation lead
- Started as Aurora MySQL business intelligence; morphed into RDS-wide OpEx platform
- Marries ticketing, bug-tracking, install-base fleet data into AI-generated executive summaries
- Delivers operational highlights, lowlights, and trends for weekly reviews and deep dives
- Previously ~10% of all RDS team bandwidth was consumed preparing weekly dashboard reports
- Adopted by 60+ teams within weeks of launch; saved thousands of engineering hours

**Changes:**
- Added Featured Launch card with `--secondary` left border and impact callout box
- Added experience bullet
- Added "60+ Teams Adopted OpEx Platform" metric tile (now 9 metric tiles total)

---

### 3. LTTR / CIT Customer Intelligence Platform

**Internal URLs:**
- prod.amsopstoolingui.rds.aws.dev/cit (ticket tracking, not linked — internal)
- groot-cit-analytics.harmony.a2z.com (builder contribution analytics, not linked — internal)

**Key facts:**
- Tracks incoming customer issues, availability incidents, and auto-cut tickets daily
- Drives LTTR (Lead Time To Resolution) insights via managed bandwidth rotation
- Previously: 30 minutes per ticket consumed at AWS scale just identifying context before resolution
- Extended with builder contribution analytics layer — tracks individual/team engagement across all ticket types
- Brings full accountability and visibility to every builder without depending on weekly ops reports (previously took weeks)
- Agentic AI-first approach simplifies communication and tracking to drive early ticket resolution

**Changes:**
- Added Featured Launch card with `--secondary` left border and impact callout box
- Added experience bullet

---

### 4. Agentic AI Oncall Scheduler

**Internal URL:** prod.amsopstoolingui.rds.aws.dev/cit/schedule (not linked — internal)

**Key facts:**
- PagerDuty-equivalent built with Agentic AI + Kiro approach
- Greedy algorithm implements fair, drift-free follow-the-sun model across global geographies
- Balances primary, secondary, and technical escalation (TE) rotation tiers simultaneously
- PTO/LOA registry: builders self-register upcoming time off; algorithm avoids scheduling on vacation/holiday/weekends
- Self-service swap model: builders see their rotation frequency vs. peers; SDM-permissioned last-minute swaps
- Auto-generates bi-weekly schedules; integrates with oncall.amazon.com portal
- Previously required weeks of SDM coordination; now fully automated with fairness guarantees
- Python service with property-based test suite using `hypothesis` for algorithmic correctness guarantees
- Also uses: pytest, requests (for oncall.amazon.com API integration), packaging, Pygments

**Changes:**
- Added Featured Launch card with `--secondary` left border and impact callout box
- Added experience bullet
- Added "Greedy Algorithms" to Engineering & Operations skills

---

## Phase 12: UI Polish

**Skills grid:** Changed from `auto-fit minmax(280px, 1fr)` to fixed `repeat(4, 1fr)` — all four skill categories in one row on desktop. Skill tags and headings slightly smaller to fit. Collapses to 2 columns at ≤1024px, 1 column at ≤768px.

---

## Current Site State (June 2026)

### Sections
1. **Hero** — name, subtitle, 3 stat tiles (20+ years, $6M+, 24x), profile photo, tech tags, CTA buttons
2. **About** — 3 paragraphs + 9 metric tiles
3. **Experience** — AWS (22 bullets), NetApp Sr. Director (8 bullets), NetApp Director (7 bullets), Education (2 cards)
4. **Featured Launches & Media** — 9 cards (see below)
5. **Technical Skills & Competencies** — 4-column grid
6. **Contact** — 5-column grid (email, phone, LinkedIn, Resume PDF, Profile PDF)
7. **Footer**

### Featured Launch Cards (in order)
1. 🚀 Aurora Serverless v2 GA (2022) — 2 embedded YouTube videos
2. 🚀 Aurora MySQL Parallel Query v2 (PQv2)
3. 🚀 Aurora MySQL Parallel Export
4. 🚀 Aurora MySQL Fast Restart (2023)
5. 🤖 Aurora MySQL + Kiro Powers — Agentic AI-First (2026) — embedded MP4 video
6. 🚀 Aurora MySQL & Amazon Bedrock Integration
7. 🚀 Aurora MySQL 8.4 GA (2026)
8. 📊 Agentic AI OpEx Dashboard — AWS RDS Platform
9. 🎯 LTTR / CIT Customer Intelligence Platform
10. ⏰ Agentic AI Oncall Scheduler — Follow-the-Sun

### Metric Tiles (9)
| Value | Label |
|-------|-------|
| 20+ | Years of Engineering Leadership |
| 3,000+ | CRs Delivered (VC 3.05) |
| 40% | Crash Reduction (3.02.1) |
| 24x | Faster Restarts (120s → 5s) |
| $6M+ | Annual CapEx Savings |
| 28% | Storage Node CapEx Reduced |
| 15+ | Fortune-10 & Enterprise Escalations |
| 56% | Ops Burden Reduced (AI/ML) |
| 60+ | Teams Adopted OpEx Platform |

### Skills (4 columns)
| Cloud & Infrastructure | Database & Data | Engineering & Operations | Leadership |
|------------------------|-----------------|--------------------------|------------|
| AWS Aurora MySQL | Parallel Query | DevOps & Pipelines | Strategic Planning |
| Serverless Database | Parallel Export | CI/CD | Operational Excellence |
| Cloud Computing | Aurora Streams | SRE Management | Global Teams |
| AWS Cloud Infra | ZeroETL | AI/ML Integrations | P&L Management |
| Hybrid Cloud Storage | Zero Downtime Upgrades | Agentic AI (MCP) | Mentoring & Hiring |
| Distributed Systems | MySQL Version Currency | Greedy Algorithms | Incident Command |
| | MySQL Databases | Automation | |
| | | Observability | |

---

## File Structure

```
GitHub_web/
├── index.html                  # Main portfolio page (all content + JS)
├── styles.css                  # Design system (aurora theme, light/dark, responsive)
├── ykreddy.jpg                 # Profile photo
├── YUGANDHAR REDDYW.pdf        # Downloadable resume
├── KYR_timeline_profile.pdf    # Downloadable experience timeline
├── banner.png                  # OG/Twitter meta image
├── README.md                   # Project description
└── context.md                  # This file — full build history
```

---

## Key Design Decisions

1. **Single-page app** — all sections on one page with smooth scroll nav
2. **Aurora color palette** — `#0b3d2e → #0d6b58 → #1a8a7a → #2d6b8a → #4a3f8a` (green-teal-blue-purple)
3. **External CSS** — `styles.css` design system (originally from pranav_html reference)
4. **Light mode default** — dark mode via `[data-theme="dark"]` with localStorage persistence
5. **Hamburger nav on mobile** — collapses to vertical menu below 768px
6. **Recruiter-optimized** — action verbs, front-loaded metrics, AWS card with `--primary` left border
7. **Card visual hierarchy** — `--primary` border = AWS experience, `--accent` border = Agentic AI / Kiro, `--secondary` border = internal platforms
8. **Featured Launches** — YouTube iframes + CloudFront MP4 `<video>` + AWS blog/doc links
9. **4-column skills grid** — fixed columns on desktop, responsive collapse
10. **Downloadable assets** — Resume and Profile PDFs in contact section

---

## CSS Theme Variables (current)

### Light Mode (`:root`)
```css
--primary: #1a8a7a;
--primary-dark: #0d6b58;
--secondary: #2d6b8a;
--accent: #4a3f8a;
--text-dark: #0f172a;
--text-medium: #334155;
--text-light: #64748b;
--bg-light: #f0faf8;
--bg-body: #ffffff;
--bg-card: #ffffff;
--bg-nav: rgba(255, 255, 255, 0.98);
--border: #d1e8e4;
--shadow: rgba(0, 0, 0, 0.08);
--shadow-hover: rgba(26, 138, 122, 0.25);
--footer-bg: #0b3d2e;
```

### Dark Mode (`[data-theme="dark"]`)
```css
--bg-body: #0a1f1a;
--bg-card: #0f2b26;
--bg-light: #0f2b26;
--bg-nav: rgba(10, 31, 26, 0.98);
--border: #1a4a3e;
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
| ≤1024px | Tablets/small laptops | Hero stacks, metrics 4 cols, skills 2 cols |
| ≤768px | Tablets portrait/large phones | Hamburger nav, all grids 1 col, contact stacks |
| ≤480px | Phones | Smaller fonts, CTA buttons stack, compact metrics/cards |

---

## All External Links (for reference)

### AWS Blog / What's New
- Serverless v2: https://aws.amazon.com/blogs/aws/amazon-aurora-serverless-v2-is-generally-available-instant-scaling-for-demanding-workloads/
- Kiro Powers What's New: https://aws.amazon.com/about-aws/whats-new/2026/05/amazon-aurora-mysql-kiro-powers/
- Kiro Powers Blog: https://aws.amazon.com/blogs/database/guide-your-amazon-aurora-mysql-migration-with-kiro-powers/
- Aurora MySQL 8.4 Blog: https://aws.amazon.com/blogs/database/amazon-aurora-mysql-8-4-is-now-generally-available/
- Fast Restart: https://aws.amazon.com/about-aws/whats-new/2023/10/amazon-aurora-mysql-reduce-database-restart-time/
- Bedrock Integration: https://aws.amazon.com/blogs/database/integrate-amazon-aurora-mysql-and-amazon-bedrock-using-sql/

### AWS Documentation
- PQv2: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-mysql-parallel-query.html
- Parallel Export: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-export-snapshot.parallel.html
- MCP Server: https://awslabs.github.io/mcp/servers/mysql-mcp-server

### YouTube (embedded)
- Overview: https://www.youtube.com/watch?v=xKFA6PJgp0o
- Deep Dive: https://www.youtube.com/watch?v=Kap0I5g1AbI

### Video (CloudFront MP4, embedded via `<video>` tag)
- Kiro Powers demo: https://d2908q01vomqb2.cloudfront.net/artifacts/DBSBlogs/DBBLOG-5632/power-edit.mp4?_=1

---

## Profile Information

- **Name:** Yugandhar Reddy
- **Current Role:** Head of Engineering, Aurora MySQL — Amazon Web Services (AWS)
- **Location:** San Francisco Bay Area / Palo Alto, CA
- **Start at AWS:** Dec 2021
- **Prior:** 21 years at NetApp (Sr. Director HCI/SRE Engineering, Director CPE, multiple positions)
- **Education:** MS Electrical & Computer Engineering (Wichita State University); BS Electrical & Electronics Engineering (Osmania University)
- **Email:** yugreddy@yahoo.com
- **Phone:** 408-569-1265
- **LinkedIn:** https://www.linkedin.com/in/yugreddy
- **Profile photo:** `ykreddy.jpg`

---

## How to Continue Building

1. Open workspace at `/Users/ykreddy/Desktop/GitHub_web` in VS Code
2. Use Live Server to preview at `http://127.0.0.1:5501/index.html`
3. To add a new deliverable: add a card in the `#launches` section and a bullet in the AWS `#experience` card
4. To add a new metric: add a `<div class="metric-box">` in the metrics-grid
5. To deploy: `git init && git add . && git commit -m "msg" && git push` to GitHub → enable GitHub Pages on `main` branch
