# Mode: evaluate — Complete Evaluation A-F

When the candidate pastes a listing (text or URL), ALWAYS deliver all 6 blocks:

## Step 0 — Archetype Detection

Classify the listing into one of the archetypes (see `_shared.md` and `_profile.md`). If it's a hybrid, indicate the 2 closest. This determines:
- Which proof points to prioritize in Block B
- How to rewrite the summary in Block E
- Which STAR stories to prepare in Block F

## Block A — Role Summary

Table with:
- Detected archetype
- Domain (platform/distributed/SaaS/cloud/enterprise)
- Function (build/consult/manage/deploy)
- Seniority
- Remote (full/hybrid/onsite)
- Team size (if mentioned)
- TL;DR in 1 sentence

## Block B — CV Match

Read `cv.md`. Create table mapping each JD requirement to exact CV lines.

**Adapted to archetype:**
- If Distributed Systems → prioritize infrastructure, scale, durability proof points
- If Enterprise SaaS → prioritize multi-tenant architecture, auth, API design
- If Cloud/DevOps → prioritize cost optimization, Terraform, CI/CD, monitoring
- If SA → prioritize system design and integrations
- If General Backend → prioritize breadth across all proof points

**Gaps** section with mitigation strategy for each. For each gap:
1. Is it a hard blocker or a nice-to-have?
2. Can the candidate demonstrate adjacent experience?
3. Is there a portfolio project that covers this gap?
4. Concrete mitigation plan (phrase for cover letter, quick project, etc.)

## Block C — Level and Strategy

1. **Detected level** in the JD vs **candidate's natural level for that archetype**
2. **"Sell senior without lying" plan**: specific phrases adapted to the archetype, concrete achievements to highlight, how to position experience as an advantage
3. **"If they downlevel me" plan**: accept if comp is fair, negotiate 6-month review, clear promotion criteria

## Block D — Comp and Demand

Use WebSearch for:
- Current salaries for the role (Glassdoor, Levels.fyi, Blind, AmbitionBox)
- Company's compensation reputation
- Role demand trend

Table with data and cited sources. If no data available, say so instead of inventing.

## Block E — Customization Plan

| # | Section | Current State | Proposed Change | Why |
|---|---------|---------------|-----------------|-----|
| 1 | Summary | ... | ... | ... |
| ... | ... | ... | ... | ... |

Top 5 CV changes + Top 5 LinkedIn changes to maximize match.

## Block F — Interview Plan (ON REQUEST ONLY)

**Skip this block by default.** Only generate when the user explicitly asks for interview prep for a specific role. This saves tokens during batch evaluation.

When requested, include:
- 6-10 STAR+R stories mapped to JD requirements
- 1 recommended case study
- Red-flag questions and answers
- Story bank update if `interview-prep/story-bank.md` exists

---

## Post-evaluation

**ALWAYS** after generating blocks A-F:

### 1. Save report .md

Save complete evaluation in `reports/{score}-{company-slug}-{YYYY-MM-DD}.md`.

- `{score}` = overall match score (e.g. `3.5`, `4.0`)
- `{company-slug}` = company name in lowercase, no spaces (use hyphens)
- `{YYYY-MM-DD}` = current date

**Report format:**

```markdown
# Evaluation: {Company} — {Role}

**Date:** {YYYY-MM-DD}
**Archetype:** {detected}
**Score:** {X/5}
**PDF:** {path or pending}

---

## A) Role Summary
(complete Block A content)

## B) CV Match
(complete Block B content)

## C) Level and Strategy
(complete Block C content)

## D) Comp and Demand
(complete Block D content)

## E) Customization Plan
(complete Block E content)

## F) Interview Plan
(complete Block F content)

## G) Draft Application Answers
(only if score >= 4.5 — draft answers for the application form)

---

## Extracted Keywords
(list of 15-20 keywords from JD for ATS optimization)
```

### 2. Register in tracker

**ALWAYS** register in `data/applications_tracker.md`:
- Next sequential number
- Current date
- Company
- Role
- Score: match average (1-5)
- Status: `Evaluated`
- PDF: ❌ (or ✅ if auto-pipeline generated PDF)
- Report: relative link to report .md (e.g., `[001](reports/001-company-2026-01-01.md)`)

**Tracker format:**

```markdown
| # | Date | Company | Role | Score | Status | PDF | Report |
```
