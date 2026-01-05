# Execution Evidence Repository

**Repository Type**: Evidence Archive (Read-Only)

**Status**: Locked (No Interpretation Allowed)

---

## ⚠️ Critical Warning

This repository contains **read-only evidence artifacts**.

- ❌ No interpretation
- ❌ No discussion
- ❌ No implementation details

It exists solely to preserve raw decision evidence produced by upstream systems and defined by the [AJT specification](https://github.com/Nick-heo-eg/spec).

**This is not a documentation repository. This is an evidence vault.**

---

## Purpose

Evidence repository for judgment STOP events.

Read-only incident logs and artifacts.
No interpretation.
No discussion.
No attribution.

**This repository contains factual execution artifacts only.**
**It does not assert intent, reasoning, or responsibility.**

---

## What This Contains

- Incident logs (what happened)
- Artifacts (screenshots, STOP reports, execution logs)
- Postmortem analyses (after-the-fact reconstruction)

## What This Does NOT Contain

- Interpretation of events (facts only)
- Normative claims ("should have" statements)
- Design principles (those belong in external constitution repos)
- Attribution of decision-makers

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
ATTRIBUTION.md             # Attribution policy
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
- No Recommendations (those belong in design repos)

**See**: `templates/POSTMORTEM_TEMPLATE.md`

---

## Relationship to Other Repositories

**Design/Constitution Repos**:
- Define what SHOULD happen (norms)
- Contain STOP rules, principles, architecture
- **Normative** (this is how system is designed)

**This Repo** (Execution Evidence):
- Records what DID happen (facts)
- Contains incidents, artifacts, postmortems
- **Descriptive** (this is what occurred)

**Direction of Reference**:
- Evidence → Constitution (incident cites violated rule)
- Constitution → Evidence (example incidents linked)

---

## Contribution Rules

**Pull Requests**: Disabled (evidence is not collaborative)

**Issues**: Disabled (this is not a bug tracker)

**Discussions**: Disabled (interpretation belongs elsewhere)

**Who Can Write**:
- Only automated execution logs from judgment execution systems
- Manual incident reports (following template strictly)
- Postmortems (only when boundary violated)

**Who Can Read**: Everyone (public repo)

---

## Time Axis

**Constitution Repos**: Fixed time axis
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

**This repo specifically does NOT**:
- Interpret why events happened (descriptive only)
- Recommend changes to STOP rules (evidence, not design)
- Provide analysis of trends (raw data only)
- Serve as issue tracker (not a bug database)
- Attribute decisions to specific systems or agents

---

## Citation

When referencing incidents from this repo:

```
Incident Log 001, Judgment Execution Evidence Repository
Repository: https://github.com/Nick-heo-eg/judgment-execution-evidence
Timestamp: [incident timestamp]
Accessed: [access date]
```

**Note**: Cite specific incident, not "the repo" (evidence is granular).

---

## Contact

**For Incident Submission**: Follow template format, submit PR to `/incidents/`

**For Questions About Evidence**: Not supported (evidence speaks for itself)

**For Design Questions**: See constitution repositories

---

## Status

**Repository Type**: Evidence Archive

**Modification Rights**: Append-only (new incidents), immutable (past incidents)

**Current Incident Count**: 0 (initial structure only)

**Last Structure Update**: 2026-01-05

---

## Final Statement

**This repository does not explain what should happen.**

**This repository records what did happen.**

**Interpretation lives elsewhere.**

**No component, system, or agent is attributed as the decision-maker in this repository.**

**Artifacts represent execution state only.**
