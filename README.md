# Execution Evidence Repository

**Repository Type**: Evidence Archive (Read-Only)

**Status**: Locked (No Interpretation Allowed)

---

## Purpose

This repository contains **execution evidence** from the Echo Judgment System.

**What This Contains**:
- Incident logs (what happened)
- Artifacts (screenshots, STOP reports, execution logs)
- Postmortem analyses (after-the-fact reconstruction)

**What This Does NOT Contain**:
- Interpretation of events (facts only)
- Normative claims ("should have" statements)
- Design principles (those belong in Boundary Constitution repo)

---

## Repository Rules

### 1. Read-Only Nature

**This repository is write-once, read-forever.**

- Incident logs are **never modified** after creation
- Artifacts are **never deleted**
- Postmortems are **never edited** (corrections → new postmortem)

**Reason**: Evidence loses validity if modified.

---

### 2. No Interpretation Allowed

**Files in this repo contain facts, not judgments.**

**Allowed**:
- "STOP rule triggered: destructive_action_detected"
- "Human decision: Abort"
- "Execution time: 2.3 seconds"

**Not Allowed**:
- "This STOP was unnecessary" (judgment)
- "Rule should be relaxed" (design opinion)
- "Better approach would be..." (recommendation)

**Enforcement**: Evidence files use template format. Deviation = rejected.

---

### 3. Postmortem Creation Rules

**Postmortems are ONLY created when:**

1. STOP boundary was violated (execution reached unsafe state)
2. Classifier failed (wrong category assigned)
3. Telemetry revealed unexpected pattern (statistical anomaly)

**Postmortems are NOT created when:**

- System worked as intended (even if STOP triggered)
- Human chose abort (expected behavior)
- No boundary violation occurred

**Template**: See `POSTMORTEM_TEMPLATE.md`

**Philosophy**: "Nothing happened" is not evidence of failure.

---

## Directory Structure

```
/incidents/
  INCIDENT_LOG_001.md       # First incident record
  POSTMORTEM_001.md         # Analysis (if boundary violated)
  INCIDENT_LOG_002.md
  ...

/artifacts/
  screenshots/
    incident_001_page.png
    incident_001_stop.png
  stop_reports/
    incident_001_report.json
    incident_001_report.md
  execution_logs/
    incident_001_execution.log

/templates/
  INCIDENT_LOG_TEMPLATE.md
  POSTMORTEM_TEMPLATE.md

README.md                   # This file
```

---

## Incident Log Format

**Required Fields**:
- Incident ID (sequential, never reused)
- Timestamp (ISO 8601)
- Domain (web, local, database, etc.)
- Action Attempted
- STOP Rule Triggered (if any)
- Human Decision
- Execution Result
- Artifact Paths

**See**: `templates/INCIDENT_LOG_TEMPLATE.md`

---

## Postmortem Format

**Required Sections**:
- Incident Reference
- Boundary Violation Description
- Evidence Chain
- Root Cause (factual, not interpretive)
- System State Before/After
- No Recommendations (those belong in Boundary Constitution repo)

**See**: `templates/POSTMORTEM_TEMPLATE.md`

---

## Relationship to Other Repositories

**Boundary Constitution Repo** (https://github.com/Nick-heo-eg/EchoJudgmentSystem_v10-1):
- Defines what SHOULD happen (norms)
- Contains STOP rules, principles, architecture
- **Normative** (this is how system is designed)

**This Repo** (Execution Evidence):
- Records what DID happen (facts)
- Contains incidents, artifacts, postmortems
- **Descriptive** (this is what occurred)

**Concept Vocabulary Repo** (planned):
- Defines terms used in both repos
- Open for refinement
- **Definitional** (this is what we mean by X)

**Direction of Reference**:
- Evidence → Constitution (incident cites violated rule)
- Constitution → Evidence (example incidents linked)
- Vocabulary ← Both (terms used by both)

---

## Contribution Rules

**Pull Requests**: Disabled (evidence is not collaborative)

**Issues**: Disabled (this is not a bug tracker)

**Discussions**: Disabled (interpretation belongs elsewhere)

**Who Can Write**:
- Only automated execution logs from headed_executor
- Manual incident reports (following template strictly)
- Postmortems (only when boundary violated)

**Who Can Read**: Everyone (public repo)

---

## Time Axis

**Boundary Constitution Repo**: Fixed time axis
- Locked at specific git tags
- Changes require new version (not edits)
- Represents "system as designed at time T"

**This Repo**: Cumulative time axis
- Append-only
- Never remove past evidence
- Represents "all events that occurred from T₀ to Tₙ"

**Why Separate**: Different modification permissions, different temporal semantics.

---

## What "Read-Only" Means

**Not Frozen**: New incidents can be added

**But Immutable**: Past incidents cannot be changed

**Structure**:
```
2025-01-15: Incident 001 created → LOCKED forever
2025-01-20: Incident 002 created → LOCKED forever
2025-02-01: Incident 003 created → LOCKED forever
```

**No Retroactive Editing**: If Incident 001 was wrong, create Incident 004 (correction), don't edit 001.

**Reason**: Evidence trails must be auditable.

---

## Non-Goals

See Boundary Constitution repo's NON-GOALS.md for full list.

**This repo specifically does NOT**:
- Interpret why events happened (descriptive only)
- Recommend changes to STOP rules (evidence, not design)
- Provide analysis of trends (raw data only)
- Serve as issue tracker (not a bug database)

---

## Citation

When referencing incidents from this repo:

```
Incident Log 001, Echo Judgment System Execution Evidence
Repository: https://github.com/Nick-heo-eg/echo-judgment-execution-evidence
Timestamp: [incident timestamp]
Accessed: [access date]
```

**Note**: Cite specific incident, not "the repo" (evidence is granular).

---

## Contact

**For Incident Submission**: Follow template format, submit PR to `/incidents/`

**For Questions About Evidence**: Not supported (evidence speaks for itself)

**For Design Questions**: See Boundary Constitution repo

**For Term Definitions**: See Concept Vocabulary repo (when created)

---

## Status

**Repository Type**: Evidence Archive

**Modification Rights**: Append-only (new incidents), immutable (past incidents)

**Current Incident Count**: 0 (initial structure only)

**Last Structure Update**: 2025-12-20

---

## Final Statement

**This repository does not explain what should happen.**

**This repository records what did happen.**

**Interpretation lives elsewhere.**
