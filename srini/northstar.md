# Northstar — Job Search Strategy & System Guide

---

## The Big Picture

**Srinivas Ravi** — 7-year senior backend engineer (Amazon S3 → Salesforce/Tableau → Aug 2024 career gap → present). Turning `jobsearch-copilot` (clone of santifer's career-ops) into a tailor-made job search tool.

**The goal is not "customize career-ops." The goal is "make this MY tool."**

The system should not carry any santifer or Yash configs blindly. Every config exists because it serves Srinivas's search. If a default from upstream or a fork doesn't apply, it's removed / modified as per Srinivas's requirements.

---

## Phased Strategy

### Phase 1a: Remote Global Roles — Pure Backend (START HERE)
- Use santifer's system as-is (no Yash fork integration)
- Target remote roles globally that allow staying in India
- CV = Amazon S3 + Salesforce/Tableau backend experience only
- Career gap (Aug 2024 → Apr 2026, ~20 months) acknowledged honestly. No spin.
- Goal: learn the system, get reps evaluating JDs, generating CVs, tailor it

### Phase 1b: Add India Targeting
- Cherry-pick from Yash's fork: India portals, LPA format, Indian cultural signal detection
- Only if integration is low-cost and easily debuggable. Otherwise defer.
- Target India hybrid/on-site roles alongside remote

### Phase 2: Switch to Dual-Track
- Prerequisites: AI proof points are solid (see "Building AI Proof" section below)
- Update cv.md with AI/Agentic section backed by real work
- Switch archetypes to dual-track (Backend primary + AI/Agentic primary)
- Retarget portals and keywords
- Germany/EU roles with visa assistance score 5.0 at this phase

---

## Building AI Proof (Independent Track — Prerequisite for Phase 2)

This is not a numbered phase. It runs in parallel with Phase 1a/1b. Phase 2 is unblocked when this has 1-2 solid proof points.

Two distinct types of proof, tracked separately:

| Type | What it proves | Examples |
|------|---------------|----------|
| **Type A: Backend engineer in AI ecosystem** | Existing backend skills are real and relevant to AI tooling | Contributing to vLLM's serving layer, LangChain's storage backend, Ray's scheduler, LlamaIndex's retrieval infrastructure |
| **Type B: AI engineer on distributed systems** | Can do actual AI engineering, and backend experience makes it production-grade | Distributed RAG with sharding/replication, multi-agent orchestration with fault tolerance, ML-powered anomaly detection for distributed systems, intelligent autoscaling with ML prediction |

- Type A = "I'm a backend engineer who can work in AI."
- Type B = "I'm an AI engineer whose backend experience is a differentiator."

> The bar: irrefutable proof that AI engineering knowledge is more than average — demonstrated through work on large open-source systems where the contribution is visible and verifiable.

---

## The Dual-Track Vision (Phase 2 target)

Kept here for reference. This is where we're heading, not where we start.

**Track A (proven):** Senior Backend / Distributed Systems Engineer — 7 years, Amazon S3, Salesforce/Tableau
**Track B (building):** AI/Agentic Systems Engineer — actively building projects, targeting roles

The combination that's hard to hire:
> "Backend engineer who built S3's control plane and Tableau Cloud's multi-tenant auth, now building AI agent systems on top of that same distributed systems muscle."

### Career Gap Framing (for when dual-track is active)
> "After 7 years building storage infrastructure at Amazon S3 and identity systems at Salesforce/Tableau, I took a deliberate break to go deep into AI/LLM/Agentic systems — [specific projects, courses, contributions]. Now I'm looking for backend-heavy AI roles where distributed systems expertise meets agent infrastructure."

---

## Phase 1a Onboarding — Backend Only, Remote Global

### Archetypes

| Archetype | fit | What they buy | Proof |
|-----------|-----|--------------|-------|
| **Distributed Systems / Platform Backend** | primary | Someone who built S3's control plane | S3 storage, 75k hosts, $2M savings |
| **Enterprise SaaS Backend** | primary | Multi-tenant, identity, auth expertise | Tableau Cloud Manager, OAuth/SAML/PKI |
| **Cloud Infrastructure / DevOps** | secondary | Terraform, ECS, Lambda, cost optimization | 40% cost reduction, ECS Fargate |

### Location Scoring (Phase 1)

| Location | Score | Notes |
|----------|-------|-------|
| Remote (Truly remote, no restrictions) | 5.0 | Top preference |
| Remote (if job expects to be India based even in Remote) | 5.0 | Second preference |
| India Hybrid/On-site (Mumbai) | 4.0 | Third preference |
| Germany (with visa assistance) | 4.0 | Third preference, only if visa sponsorship explicitly mentioned |
| EU (other, with visa) | 3.5 | Open but lower priority |
| Other | case-by-case | |

### Location Scoring (Phase 2 — when dual-track is active)

| Location | Score | Notes |
|----------|-------|-------|
| Remote (India-based) | 5.0 | |
| Germany / EU (with visa assistance) | 5.0 | Elevated at Phase 2 |
| India Hybrid/On-site (Mumbai) | 4.5 | |
| Other | case-by-case | |

### Files to create (Phase 1a)

| Step | File | What it contains |
|------|------|-----------------|
| **0** | — | `npm install` + `npx playwright install chromium` |
| **1** | `cv.md` | Pure backend CV from applicant_profile.yaml. No AI section. |
| **2** | `modes/_profile.md` | Backend-only archetypes, adaptive framing, exit narrative, superpowers, proof points, comp, WLB policy, product-only filter, negotiation scripts. No santifer/Yash archetype remnants. |
| **3** | `config/profile.yml` | Backend archetype config, narrative, comp (₹25 LPA floor, no ceiling), location (Mumbai + Remote) |
| **4** | `portals.yml` | Remote-global portals from santifer. Backend/Java/Spring/Distributed Systems keywords. Product-only filter. German market boards included (enabled, English-language roles). |
| **5** | `data/applications.md`, `data/pipeline.md` | Empty tracker + pipeline |
| **6** | — | `npm run doctor` to validate |

Note: No `_shared.md` modifications in Phase 1a. Use santifer's upstream as-is. Yash's India market rules come in Phase 1b.

### What stays from santifer
- Evaluation engine, PDF generation, interview-prep, patterns, story bank, scanner
- All 14+ modes (in Spanish — they work fine, can translate later if needed)
- Canva MCP integration (plug-and-play, keep available, no investment needed)
- German market boards (keep enabled)

### What gets removed/skipped
- santifer's default archetypes (AI-only — replaced with our backend archetypes in `_profile.md`)
- Spanish market boards (not relevant)
- Any config that targets santifer's profile (he's an AI/automation Head, we're backend)

---

## Design Decisions

| Decision | Resolution |
|----------|-----------|
| **Archetypes** | Phase 1: Backend-only. Phase 2: add AI/Agentic track. |
| **CV** | Phase 1: Pure backend. Phase 2: Add AI section with real proof. |
| **Career gap** | Acknowledged honestly. No spin in Phase 1. Narrative pivot in Phase 2 when proofs exist. |
| **Comp** | **₹25 LPA floor, no ceiling.** Work quality > salary. |
| **WLB** | First-class scoring signal. Hard penalize: rotational shifts, mandatory on-site, crunch culture, >50hr/week. |
| **Product companies only** | Filter out service companies (TCS, Infosys, Wipro, Cognizant, HCL, Tech Mahindra, LTIMindtree, Mphasis, etc.). Flag outlier service cos that do genuine product work as exceptions. |
| **Deal-breakers** | Service companies, mandatory 5-day on-site (unless exceptional WLB), crunch signals, rotational shifts. |
| **Java** | Core skill. Target Java-heavy roles. |
| **Canva** | Keep as plug-and-play. Don't invest in building for it. |
| **German boards** | Keep enabled. German A1 proficiency — most remote roles at German companies post in English. |
| **Yash's fork** | Phase 1a: don't integrate. Phase 1b: cherry-pick India portals, LPA format, cultural signals only if low-cost. |

---

## Key Preferences

| Preference | Value |
|-----------|-------|
| **Track (Phase 1)** | Backend only: Distributed Systems (primary), Enterprise SaaS (primary), Cloud/DevOps (secondary) |
| **Track (Phase 2)** | Dual-track: Backend + AI/Agentic (both primary) |
| **Career gap** | Honest. No spin in Phase 1. Narrative pivot in Phase 2. |
| **Comp (India)** | ₹25 LPA minimum, no ceiling. |
| **Comp (International)** | Open, no hard target yet. |
| **Location preference** | Remote (India) > India (Hybrid/Onsite Mumbai) > Germany (with visa) |
| **German proficiency** | A1 |
| **WLB** | First-class signal. Hard penalize crunch, rotational shifts, mandatory on-site. |
| **Company type** | Product companies only. No service cos except genuine outliers. |
| **Notice** | 0 days (immediately available). |
| **Stack** | Java 8-17, Spring, Python, DynamoDB, React, Terraform. |
| **Seniority** | Senior / Staff level. |

---

## Step-by-Step Workflows

These workflows are derived from the actual mode files in the repo: [scan.md](file:///Users/srinivasravi/dev/jobsearch-copilot/modes/scan.md), [evaluate.md](file:///Users/srinivasravi/dev/jobsearch-copilot/modes/evaluate.md), [apply.md](file:///Users/srinivasravi/dev/jobsearch-copilot/modes/apply.md), [auto-pipeline.md](file:///Users/srinivasravi/dev/jobsearch-copilot/modes/auto-pipeline.md), [pipeline.md](file:///Users/srinivasravi/dev/jobsearch-copilot/modes/pipeline.md).

### Steps for Job Discovery (`scan` mode)

| Step | Who | What happens |
|------|-----|-------------|
| 1 | 🤖 | Read `portals.yml` for configured portals and keywords |
| 2 | 🤖 | **Level 1 — Playwright direct**: Navigate to each company's `careers_url`, extract all visible job listings (title + URL). Most reliable — works with SPAs. |
| 3 | 🤖 | **Level 2 — Greenhouse API**: For companies with Greenhouse, fetch JSON API for structured job data. Complementary to Level 1. |
| 4 | 🤖 | **Level 3 — WebSearch queries**: Run `site:`-filtered search queries for broad discovery of companies not yet in `tracked_companies`. Results may be stale. |
| 5 | 🤖 | Filter by title using `title_filter` from `portals.yml` (positive keywords must match, negative keywords must not) |
| 6 | 🤖 | Deduplicate against 3 sources: `scan-history.tsv`, `applications.md`, `pipeline.md` |
| 7 | 🤖 | Verify liveness of Level 3 results via Playwright (Level 1+2 are inherently real-time) |
| 8 | 🤖 | Add verified new listings to `data/pipeline.md` section "Pending". Log all results (added/skipped) to `scan-history.tsv`. |
| 9 | 🤖 | Report summary: "Found X new listings. Here they are: [list]" |
| **10** | **👤 USER** | **Review the list. Say which to evaluate, or "evaluate all", or "skip".** |

### Steps for Evaluating a Job Listing (`evaluate` / `auto-pipeline` mode)

| Step | Who | What happens |
|------|-----|-------------|
| **1** | **👤 USER** | **Provide a JD URL, paste JD text, or say "process pipeline"** |
| 2 | 🤖 | Extract JD: Playwright (preferred for SPAs) → WebFetch (fallback for static) → ask user to paste (last resort) |
| 3 | 🤖 | Verify listing is still active (title + description + Apply button = active) |
| 4 | 🤖 | **Step 0 — Archetype detection**: Classify the JD against archetypes in `_profile.md` |
| 5 | 🤖 | **Block A — Role Summary**: Archetype, domain, function, seniority, remote status, TL;DR |
| 6 | 🤖 | **Block B — CV Match**: Map each JD requirement to lines in `cv.md`. Identify gaps + mitigation strategy. |
| 7 | 🤖 | **Block C — Level & Strategy**: JD seniority vs candidate's natural level. Game plan for positioning. |
| 8 | 🤖 | **Block D — Comp & Demand**: WebSearch for salary data (Glassdoor, Levels.fyi). If no data, say so — don't invent. |
| 9 | 🤖 | **Block E — CV Customization Plan**: Top 5 CV changes + Top 5 LinkedIn changes for this role. |
| 10 | 🤖 | **Block F — Interview Prep**: 6-10 STAR+R stories mapped to JD requirements. Append new ones to `interview-prep/story-bank.md`. |
| 11 | 🤖 | Save full report to `reports/{###}-{company}-{date}.md` |
| 12 | 🤖 | Generate tailored CV PDF via `modes/pdf.md` pipeline (if score >= 3.0) |
| 13 | 🤖 | If score >= 4.5: draft application answers (Section G) in the report |
| 14 | 🤖 | Register in tracker via TSV → `merge-tracker.mjs` |
| 15 | 🤖 | Present: score, fit analysis, recommendation |
| **16** | **👤 USER** | **Decide: apply, skip, or save for later** |

### Steps for Applying to a Job (`apply` mode)

| Step | Who | What happens |
|------|-----|-------------|
| **1** | **👤 USER** | **Say "apply to [company]" or open the application form** |
| 2 | 🤖 | Detect: Read active browser tab (Playwright snapshot) or ask user to share screenshot/questions |
| 3 | 🤖 | Identify company + role from the page. Search `reports/` for matching evaluation. |
| 4 | 🤖 | Load full report + Section G draft answers (if they exist). If no report exists, offer to run auto-pipeline first. |
| 5 | 🤖 | Compare: Does the role on screen match the evaluated role? If changed, alert user. |
| 6 | 🤖 | Analyze all visible form questions (text fields, dropdowns, yes/no, salary, uploads) |
| 7 | 🤖 | Generate personalized answer for each question using report proof points + cv.md |
| 8 | 🤖 | Present all answers formatted for copy-paste. Flag anything the user should review. |
| **9** | **👤 USER** | **Review all fields. Edit anything that needs changing.** |
| **10** | **👤 USER** | **Click Submit. System NEVER submits on user's behalf.** |
| 11 | 🤖 | After user confirms submission: update tracker status to "Applied". Update Section G with final answers. Suggest LinkedIn outreach. |

### Steps for Processing Pipeline (`pipeline` mode)

| Step | Who | What happens |
|------|-----|-------------|
| **1** | **👤 USER** | **Say "process pipeline" or run `/career-ops pipeline`** |
| 2 | 🤖 | Read `data/pipeline.md` → find items marked `- [ ]` in "Pending" section |
| 3 | 🤖 | Run `node cv-sync-check.mjs` — if CV is out of sync, warn user before proceeding |
| 4 | 🤖 | For each pending URL: run full auto-pipeline (Steps 2-14 from Evaluation workflow above) |
| 5 | 🤖 | If 3+ URLs pending, launch parallel agents for speed |
| 6 | 🤖 | Move processed items from "Pending" to "Processed" with score + PDF status |
| 7 | 🤖 | Mark unreachable URLs as `- [!]` with error note, continue with next |
| 8 | 🤖 | Present summary table: company, role, score, PDF status, recommended action |
| **9** | **👤 USER** | **Review results. Decide which to apply to.** |

---

## Communication Preferences

- Be direct and no fluff. Caveman like directness. Example: "Noted" when user asks for Agent's thoughts and there are no logical loopholes. No "That's a great idea/best idea." 
- No flattery. No empty encouragement. Exception is when you have proofs that the flattery wasn't empty.
- Don't make claims without evidence. Distinguish between what is known and what is speculation.

---

## System Documents

All planning and tracking docs live in `jobsearch-copilot/srini/`. The rest of the project (`data/`, `reports/`, `output/`, `modes/`, etc.) follows santifer's standard structure. `srini/` is our meta-directory — strategy, plans, tracking. Everything else follows career-ops conventions.

```
jobsearch-copilot/srini/
├── northstar.md              ← long-term strategy (this file)
├── current_plan.md           ← what we're about to execute
├── execution_tracking.md     ← task checklist during execution
├── completion_report.md      ← post-execution record
├── applicant_profile.yaml    ← raw profile data (already exists)
└── project_audit.md          ← system audit (already exists)
```

| Document | Purpose | Who edits | Lifespan |
|----------|---------|-----------|----------|
| `srini/northstar.md` | Long-term strategic alignment — who you are, what you want, the phased approach | AI drafts, user corrects in chat | Persists across conversations |
| `srini/current_plan.md` | Short-term technical plan for a specific chunk of work | AI drafts, user approves before execution | Per major task |
| `srini/execution_tracking.md` | Checklist of what's done, in progress, next | AI updates during work | Per major task |
| `srini/completion_report.md` | Post-execution record — what changed, what was tested | AI writes after completing work | Per major task |

### Human-in-the-loop checkpoints

1. **Northstar review** — after AI drafts/updates `northstar.md` → user corrects in chat
2. **Plan approval** — after `current_plan.md` is created → user says "approved" or corrects. **AI does NOT execute until approved.**
3. **During execution** — user can interrupt anytime
4. **Application submission** — AI NEVER clicks Submit. User does.
5. **Post-execution** — user verifies `completion_report.md`
