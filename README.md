# Career-Ops — Srinivas's Job Search Command Center

Forked from [santifer/career-ops](https://github.com/santifer/career-ops). Customized for a Senior Backend Engineer targeting India + global remote roles.

## What This Is

An AI-powered job search pipeline running on Antigravity (Claude). Instead of manually tracking applications in a spreadsheet, the system:

- **Scans** career portals via Greenhouse API + Playwright (84 companies scanned so far)
- **Evaluates** listings with a structured A-E scoring system against my CV
- **Generates** tailored PDFs — ATS-optimized CVs customized per JD
- **Tracks** everything in `data/applications_tracker.md` with pipeline integrity checks

> The system never submits an application — I always have the final call.

## Current Status

**Phase 1a — Scan + Evaluate** (in progress)

- 4 scan rounds complete, 84 companies scanned
- Pipeline split into 3 priority tables: Remote (Global), Remote (India), India (On-site/Hybrid)
- 10 evaluations complete (Remote Global drained)
- Next: Remote India (6 GitLab roles) → India On-site (Databricks, Zscaler, JFrog, Uber...)

## Key Files

| File | What It Does |
|------|-------------|
| `cv.md` | My CV in markdown (gitignored — has phone/email) |
| `config/profile.yml` | Profile config — archetypes, comp targets, location prefs (gitignored) |
| `modes/_profile.md` | Personalization — exit narrative, scoring weights, deal-breakers (gitignored) |
| `data/applications_tracker.md` | Application tracker, split by Remote / Remote-India / India (gitignored) |
| `data/pipeline.md` | Inbox of pending job URLs, 3 location tables (gitignored) |
| `srini/northstar.md` | **Strategic brain** — scan workflow, evaluate workflow, scoring framework |
| `srini/execution_tracking.md` | Session log — what was done, what's next |
| `srini/current_plan.md` | Phase 1a checklist |
| `portals.yml` | Companies + search queries for scanner (gitignored) |
| `reports/` | Evaluation reports, named `{score}-{company}-{date}.md` (gitignored) |
| `CLAUDE.md` | System prompt — the agent reads this every session |

## My Setup

- **Profile:** Senior Backend Engineer, 7 years (Amazon S3, Salesforce/Tableau)
- **Archetypes:** Distributed Systems, Enterprise SaaS, Cloud Infrastructure
- **Notice period:** 0 days (career break since Aug 2024)
- **Comp targets:** India min ₹25 LPA, International min $25K USD
- **Deal-breakers:** Service companies (TCS, Infosys, etc.)

### Priority Framework (Northstar)

1. Remote Global (score 5.0)
2. Remote India (score 5.0)
3. India Hybrid/On-site — Mumbai preferred (score 4.0)
4. Germany/EU with visa assistance (score 4.0/3.5)

## How to Resume Work

```bash
# 1. Open in Antigravity / Claude Code
cd ~/dev/jobsearch-copilot

# 2. The agent reads CLAUDE.md automatically and srini/northstar.md for strategy

# 3. Common commands:
#    "scan" — run another scan round
#    "evaluate Remote India" — evaluate pending roles
#    "continue" — pick up where we left off

# 4. Pipeline health check
node verify-pipeline.mjs
```

## Scripts

| Script | What It Does |
|--------|-------------|
| `verify-pipeline.mjs` | Health check — statuses, report links, duplicates |
| `merge-tracker.mjs` | Merge batch TSV additions into tracker |
| `dedup-tracker.mjs` | Remove duplicate tracker entries |
| `normalize-statuses.mjs` | Clean non-canonical statuses |
| `generate-pdf.mjs` | Playwright: HTML → PDF |

## Upstream

Forked from [santifer/career-ops](https://github.com/santifer/career-ops) — Santiago's open-source job search system. Also pulled India-specific portals from [SaravgiYash/career-ops-india](https://github.com/SaravgiYash/career-ops-india).

```
origin    → SrinivasRavi/jobsearch-copilot (this fork)
upstream  → santifer/career-ops (original)
yash      → SaravgiYash/career-ops-india (India portals)
```

## License

MIT (inherited from upstream)
