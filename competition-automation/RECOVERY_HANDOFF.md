# Competition automation — recovery handoff

## Important discovery
The user's private `errorrelooad/competition-automation` repository exists but is empty and GitHub's current connected create-file operation returned HTTP 422 (`"sha" wasn't supplied`) when initializing it. **No source was uploaded to that private repository.** This public repository is a documentation hub only; do not migrate private source here.

## Actual project source candidates in ChatGPT Library
Folder `/대회 매크로` contains:
- `competition_autopilot_membership_worker_candidate.zip` (169 archive entries; inspected)
- `competition_autopilot_v43_safety_candidate.zip` (159 entries; inspected)
- `competition-autopilot-v43.zip`, `competition-autopilot-v42.zip`, `competition-autopilot-v41.zip`
- `autopilot_worker_test_bundle.zip`, `competition_autopilot_worker_experimental_checkpoint.zip`
- `EXECUTION_ISOLATION_v43.md`, `USER_GUIDE_v43.md`, `STAGNATION_POLICY.md`, test reports
- `stage_app_socket_probe.sh`

Inspected candidate archives contain a Python package `competition_autopilot/` with `orchestrator.py`, `solution_agent.py`, `trainer.py`, `execution_sandbox.py`, `kaggle_workflow_adapter.py`, `dacon_workflow_adapter.py`, `credentials.py`, `mcp_server.py`, and GitHub Actions workflows. Therefore this project includes competition solving and workflow automation, **not just discovery of contest notices**. Earlier public docs describe only the narrower opportunity-discovery track and must not be mistaken for complete private source documentation.

## Recovery plan for next operator
1. Inventory all archive versions and calculate SHA-256 per archive and member; check zip paths for traversal.
2. Compare membership-worker candidate vs safety candidate and earlier v43. Do not assume newest timestamp equals safest baseline.
3. Scan for secrets, personal data, cached submissions, competition datasets, and third-party licensing before any push.
4. Initialize the private `competition-automation` repository with a safe initial commit using a supported GitHub client; do not push to the public hub.
5. Restore a vetted candidate on a feature branch, preserve original archives separately, run offline unit tests, and capture test output.
6. Add developer setup, architecture, risk register, and explicit status of each integration (Kaggle/DACON/Codex/MCP).
7. Adopt trace IDs, workflow step timing, error categories, cost and quality evaluation, agent action audit logs, and approval before external submissions.

## Source adaptation
The user-provided Datadog AI Playbook (2026, 18-page PDF) advocates observability, measurable SLOs, structured evaluation, and human-in-the-loop oversight. See `competition-automation/OBSERVABILITY_PLAYBOOK.md`. The existing design applies these principles to notice discovery; the private competition-solving source will require additional evaluation of training, solution validation, sandbox isolation, and submission workflows.

**Status:** handoff and discovery documented; source migration, code integration, and runtime verification not completed.
