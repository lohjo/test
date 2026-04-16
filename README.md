# AI Job Hunter Workflow Repo

Markdown-first multi-agent job-hunt workflow.

## Main Files

- Canonical pipeline: AI Job Hunter Workflow/ai-job-hunter-orchestrator.md
- Narrative companion: AI Job Hunter Workflow/ai-job-hunter-workflow.md
- Runtime rules: AI Job Hunter Workflow/execution-model.md
- User pref template: AI Job Hunter Workflow/user-preferences-template.md
- Agent specs: AI Job Hunter Workflow/agents/
- n8n full workflow: job-application-workflow.json

## Quick Run

1. Fill preferences from template.
2. Launch orchestrator command.
3. Review each phase gate before continue.

## Rules

- Orchestrator doc = single source truth.
- Narrative doc = context only.
- Gmail API optional; manual draft fallback allowed.

## n8n Notes

- Import job-application-workflow.json into n8n.
- Set credentials for Google Drive, Google Sheets, Gemini, Telegram.
- Workflow runs daily at 17:00.
- Match alert threshold = score > 70.
