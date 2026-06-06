# State Disability Policy Index (SDPI)

**QSS 20 · Dartmouth College · Chae Lee · 2026**

An interactive data visualization exploring disability policy generosity across all 50 U.S. states and the District of Columbia, built from 36 verified policy indicators across 6 domains.

🔗 **[Live Site →](https://qss-20-website.vercel.app/)** 

---

## Overview

No single official measure captures how generous U.S. states are toward people with disabilities. The SDPI fills that gap by assembling 36 indicators — scraped from federal and state government websites and verified by calling regional program officers directly — into a composite index that can be stress-tested across three normalization methods.

**Headline finding:** The Northeast mean SDPI (0.50) is 2.4× the South mean (0.20), a gap of 1.4 standard deviations driven not by outliers but by decades of divergent policy choices across income support, Medicaid generosity, community-based service infrastructure, and pandemic-era reinvestment.

---

## Features

- **Interactive choropleth map** — all 51 jurisdictions colored by SDPI score
- **Three normalization methods** — toggle between Hybrid, Min-Max, and Z-Score live
- **State detail panel** — click any state to see all 36 indicator scores, organized by domain, with mini bar charts
- **Scrolling narrative** — four story panels walk through the research question, headline finding, key insight (HCBS drives widest variation), and limitations
- **Fully static** — one HTML file, no server, no build step

---

## Data

| File | Contents |
|------|----------|
| `index.html` | Entire site with all data embedded |
| `SDPI_final_all_methods.csv` | Source data (not required for the site to run) |

### 36 Indicators across 6 Policy Domains

| Domain | Indicators |
|--------|-----------|
| **Income & Cash Support** | Avg monthly SSI payment, SSI state supplement (CAPS), UI good cause caregiving, Medicaid buy-in, subminimum wage (14c) index, SSI auto-enrollment, SSI 209(b) criteria, family responsibility classification |
| **Medicaid & Long-Term Care** | Spousal impoverishment protection, Medicaid eligibility threshold, medically needy program, ADL Medicaid coverage %, private LTC insurance per 1,000, SMD demonstration projects, initial/reconsidered/total approval rates |
| **Home & Community-Based Services** | HCBS expenditure ratio, HCBS user ratio, LTSS HCBS % (older adults), home health aides per 100k, HCBS presumptive eligibility |
| **Employment & Vocational Support** | VR spending (career), VR spending (training), special education policy score |
| **ARP / Pandemic Relief** | Caregiver & family support, waiting list diversion, tech & telehealth, cross-sector investments, workforce training, quality improvement |
| **Housing, Accessibility & Education** | Livability — transportation, livability — housing, Section 811 PRA, Section 811 % disability, FEMA state hazard mitigation plan |

### Normalization Methods

- **Min-Max** — rescales each indicator to [0, 1] based on observed state-level range
- **Z-Score** — standardizes around mean 0, SD 1 across states
- **Hybrid** *(primary)* — averages min-max and z-score normalized values; more robust to extreme outliers than either alone

### Data Sources

- Kaiser Family Foundation (KFF)
- UNH Institute on Disability / UCED
- Centers for Medicare & Medicaid Services (CMS)
- Social Security Administration (SSA)
- Federal and state government program websites (verified by phone with regional officers)

---

## Deploying

No CLI or build tools required — this is a single static HTML file.

### Step 1 — GitHub

1. Go to [github.com](https://github.com) → **New repository**
2. Name it `sdpi-website` (or anything you like), set to **Public**
3. Click **Create repository**
4. On the next screen, click **"uploading an existing file"**
5. Drag in `index.html` and `README.md` → **Commit changes**

### Step 2 — Vercel

1. Go to [vercel.com](https://vercel.com) → sign in with GitHub
2. Click **Add New → Project**
3. Find your `sdpi-website` repo → **Import**
4. Leave all settings as default → **Deploy**
5. ~30 seconds later you have a live URL like `sdpi-website.vercel.app`

Update the link at the top of this README with your Vercel URL once it's live.

---
