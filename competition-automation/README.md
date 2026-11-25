# Competition and opportunity automation

**Status: proposed architecture; implementation not verified.**

## Goal
Help students and independent builders discover competitions, grants, and programs without losing track of source provenance, eligibility rules, and deadlines.

## Proposed workflow
1. Ingest notices from permitted official sources and record source URLs and retrieval timestamps.
2. Normalize title, organizer, eligibility, opening and closing dates, and application links while retaining original text.
3. Deduplicate notices without collapsing distinct editions or deadlines.
4. Apply transparent filters and flag ambiguous eligibility for human review.
5. Produce a reviewable shortlist and optional reminders only after explicit authorization.

## Design safeguards
Respect site terms and robots guidance; prefer official feeds and APIs. Do not claim applications were submitted or deadlines confirmed without source checks. Avoid collecting personal data unnecessarily. Preserve provenance and distinguish stale notices from current opportunities.

## Verification roadmap
- Fixture-based ingestion tests for missing dates, duplicate notices, and changed deadlines.
- Human-reviewed Korean-language eligibility examples.
- Dry-run notifications before enabling scheduled delivery.
- Source-specific reliability and freshness metrics.

No live scraper, scheduler, or notification integration is claimed by this repository.
