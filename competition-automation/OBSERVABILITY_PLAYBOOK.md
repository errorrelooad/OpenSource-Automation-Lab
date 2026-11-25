# Competition Automation: Observability, Evaluation, and Governance

Status: design proposal only; no live scraper, scheduler, alerts, or applications verified.

Source: user-provided Datadog, *AI Playbook for Engineering Leaders: Building Reliable Systems at AI Velocity* (2026, 18-page PDF). The source advocates measurable outcomes, telemetry, structured evaluations, and human oversight. This document adapts those ideas to opportunity discovery; it is not a claim that Datadog recommends this specific competition workflow.

## Existing scope to preserve
The existing [project README](README.md) defines permitted official-source ingestion, provenance, normalization, deduplication, eligibility review, and explicitly authorized reminders. Do not replace these safeguards or assert deployment.

## Proposed traceable pipeline
1. **Discover:** record source URL, fetch time, response status, and source policy; respect robots and site terms.
2. **Normalize:** preserve original notice alongside structured fields and parser version.
3. **Deduplicate:** record match confidence and why notices were merged; preserve different editions and deadlines.
4. **Eligibility:** label supported / unsupported / uncertain with citations to exact official criteria; uncertain cases require review.
5. **Rank:** generate explainable recommendation score and model/prompt version, not ungrounded certainty.
6. **Notify:** use dry-run first; send reminders only when explicitly enabled. Never auto-submit applications.

## Telemetry schema (proposed)
- trace_id, run_id, source_id, notice_id, step, start_time, duration_ms, status, error_code
- source_url, retrieved_at, original_content_hash, parser_version, confidence
- model_id, prompt_version, tokens_in, tokens_out, estimated_cost (when AI is used)
- decision, reviewer_status, approval_id, notification_status

Avoid collecting applicants' personal information in telemetry. Redact credentials, session tokens, and sensitive source content.

## Quality metrics and acceptance tests
| Measure | Definition | Initial verification |
| --- | --- | --- |
| Source success rate | successful allowed fetches / attempted allowed fetches | fixture and dry-run |
| Freshness | elapsed time since last verified official notice | source-specific |
| Duplicate precision | correct merges / all proposed merges | human-labeled fixtures |
| Eligibility accuracy | correct classifications / reviewed examples | Korean-language review set |
| Deadline-change detection | detected known changes / known changes | dated fixture revisions |
| Notification accuracy | correct authorized reminders / delivered reminders | dry-run first |
| Cost per processed notice | total model and infrastructure cost / processed notices | measure only after deployment |

Thresholds must be set after baseline measurements; no production numbers are currently available.

## Human approval and governance
- Read-only discovery and local evaluation may run within granted scope.
- Source-policy violations, uncertain eligibility, changes to notification destinations, and public posts require review.
- Applications, form submission, external messages, and uploads require explicit user approval.
- Log agent identity, scoped tool permissions, action rationale, approval, and result.

## Rollout and validation
- Days 1-30: inventory source permissions, existing code, and baseline fixtures.
- Days 31-60: add structured logs, trace IDs, source freshness checks, and evaluation datasets.
- Days 61-90: pilot dry-run scheduling and human-approved notifications; review audit trails and rollback.

## GitHub workflow
Develop on a feature branch, add deterministic fixture tests, verify no private information is committed, review changes, then merge after approval. This public repository is a documentation/research hub; do not copy private JARVIS code or private datasets into it.

## Exclusions
No claims of working production integration or live scraping. No BC-250-related work. The original PDF has not been copied to this repository.
