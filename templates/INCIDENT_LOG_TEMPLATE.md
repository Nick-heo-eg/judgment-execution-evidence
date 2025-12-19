# Incident Log [ID]

**Incident ID**: [Sequential number, format: 001, 002, ...]

**Timestamp**: [ISO 8601 format: YYYY-MM-DDTHH:MM:SS+00:00]

**Domain**: [web | local | database | network | other]

**Status**: [STOP_TRIGGERED | EXECUTED | ABORTED | SKIPPED]

---

## Action Attempted

**Action Type**: [navigate | click | delete_file | run_command | query_database | etc.]

**Parameters**:
```yaml
[Copy exact parameters from TaskSpec]
```

**Preview** (if available):
```
[What WOULD have executed - exact command/action]
```

---

## STOP Rule Check

**Rules Checked**: [List all rules that were evaluated]

**Rule Triggered**: [Rule name, or "None" if passed]

**Trigger Reason**: [Exact reason string from StopResult]

**Trigger Details**:
```
[Additional context: which element detected, which pattern matched, etc.]
```

---

## Human Decision

**Decision Prompt Shown**: [Yes | No]

**Decision Options**: [Continue | Abort]

**Human Choice**: [continue | abort | N/A if no decision required]

**Decision Timestamp**: [When human responded]

---

## Execution Result

**Execution Status**: [completed | skipped | failed | N/A]

**Result Details**:
```
[stdout/stderr if command]
[Page state if web action]
[Error message if failed]
```

**Execution Duration**: [seconds, or N/A]

---

## Artifacts

**Artifact Directory**: `artifacts/incident_[ID]/`

**Files**:
- Screenshot (web): `artifacts/screenshots/incident_[ID]_page.png`
- STOP Report: `artifacts/stop_reports/incident_[ID]_report.md`
- Execution Log: `artifacts/execution_logs/incident_[ID].log`
- [Other artifacts as needed]

---

## Context

**Task ID**: [From TaskSpec, if available]

**Step Number**: [Which step in task sequence]

**Previous Steps**: [How many steps completed before this]

**System State**:
```
[CWD for local, URL for web, relevant state snapshot]
```

---

## Telemetry

**Logged to Telemetry**: [Yes | No]

**Telemetry Event ID**: [UUID from telemetry log, if applicable]

**Telemetry File**: [Path to JSONL entry]

---

## Boundary Analysis

**Boundary Violated**: [Yes | No]

**Expected Behavior**: [What should have happened according to STOP rules]

**Actual Behavior**: [What did happen]

**Postmortem Required**: [Yes | No]

**Postmortem Reference**: [POSTMORTEM_[ID].md if created]

---

## Notes

**Observations** (factual only, no interpretation):
- [Observation 1]
- [Observation 2]

**DO NOT INCLUDE**:
- Why this happened (interpretation)
- What should be changed (recommendation)
- Whether STOP was "correct" (judgment)

---

## Metadata

**Created**: [Timestamp]

**Created By**: [human | automated_executor]

**Last Modified**: [Never - incidents are immutable]

**Related Incidents**: [List IDs if part of sequence]

---

## Template Version

**Version**: 1.0

**Last Updated**: 2025-12-20
