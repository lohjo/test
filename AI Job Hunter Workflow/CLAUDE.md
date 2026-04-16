# CLAUDE Memory - AI Job Hunter Workflow

## Canonical Docs

- Source truth: [ai-job-hunter-orchestrator.md](ai-job-hunter-orchestrator.md)
- Narrative only: [ai-job-hunter-workflow.md](ai-job-hunter-workflow.md)
- Runtime + delivery: [execution-model.md](execution-model.md)

## Agent Roles

- WorkflowArchitect: map branches, contracts, failures.
- DocumentGenerator: build XLSX.
- JobScorerOutreachSpecialist: filter, score, outreach drafts.
- ExecutiveSummaryGenerator: optional SCQA summary.

## Hard Constraints

- Search window = 14 days.
- Pass threshold = score >= 7 unless user override.
- Retries = max 2 per phase.
- No hallucinated jobs or manager contacts.

## Decision Log

- Orchestrator doc stay canonical. Stop drift.
- Broad RecruitmentSpecialist kept for reference.
- Pipeline use focused scorer/outreach agent.
- Gmail behavior: API primary, markdown fallback.
