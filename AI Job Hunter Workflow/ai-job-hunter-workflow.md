# AI Job Hunter Workflow (Narrative)

Status: narrative companion doc.
Canonical pipeline logic lives in ai-job-hunter-orchestrator.md.

## Purpose

This file gives quick human-readable intent for non-technical review.
Do not duplicate executable phase logic, contracts, or code snippets here.

## Workflow Intent

1. Collect user preferences.
2. Search fresh jobs (14-day window).
3. Save structured listings to XLSX.
4. Filter and score jobs.
5. Generate personalized outreach drafts.
6. Deliver package for review.

## Canonical References

- Pipeline source: ai-job-hunter-orchestrator.md
- Runtime behavior: execution-model.md
- Preferences input: user-preferences-template.md
- Focused scorer agent: agents/job-hunt-scorer-outreach-specialist.md

## Guardrails

- No hallucinated job data.
- Compliance-first language and privacy.
- Gate-by-gate user review before proceed.

## Change Policy

If phase logic changes, update only ai-job-hunter-orchestrator.md.
Keep this doc short and stable.
