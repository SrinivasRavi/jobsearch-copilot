# Current Plan: Phase 1a — Onboarding Complete, Now Scanning

## Status: Scanning for remote-global backend roles

Phase 1a onboarding is complete:
- [x] `npm install` + `npx playwright install chromium`
- [x] `cv.md` — Pure backend CV (Amazon S3 + Salesforce/Tableau + Accenture)
- [x] `modes/_profile.md` — Backend-only archetypes, WLB scoring, deal-breakers
- [x] `config/profile.yml` — Personal data, comp targets (₹25 LPA floor)
- [x] `portals.yml` — Backend/Java/Spring keywords, product-only filter
- [x] `data/applications.md` + `data/pipeline.md` — Tracker + pipeline initialized
- [x] `npm run doctor` — All checks passed
- [x] Spanish → English translation of all mode files

## Current Task: Job Discovery (scan mode)

### Strategy (from northstar.md)
1. **Remote-global roles first** — truly remote, no location restrictions
2. **India-remote roles second** — remote but India-based
3. **India hybrid/on-site third** — Mumbai preferred

### Technique: Greenhouse API (Level 2 — fastest)
- Hit all 30 tracked company APIs in `portals.yml`
- Filter by backend title keywords
- Filter by remote/global location
- Add matches to `data/pipeline.md`

### Progress
- [x] Round 1: Greenhouse API scan — 30 companies, 412 raw → 10 viable (India + remote)
- [x] Nasdaq evaluation — Score 4.0/5, recommended Apply
- [ ] Round 2: More Greenhouse API — expand to companies NOT in portals.yml
- [ ] Evaluate top pipeline items (Glean Backend, Celonis Java, Uber Java Platform)
- [ ] Continue scanning with WebSearch (Level 3) for broader discovery

### Pipeline
15 roles in `data/pipeline.md` — awaiting evaluation.

## What's NOT in scope right now
- Playwright scanning (Level 1) — slower, use only if API unavailable
- Phase 1b India-specific integration (Yash's fork)
- AI/Agentic track (Phase 2)
