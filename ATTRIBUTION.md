# Attribution Policy

## Statement of Non-Attribution

**No component, system, or agent is attributed as the decision-maker in this repository.**

**Artifacts represent execution state only.**

---

## What This Means

This repository contains factual records of execution events.

**It does NOT**:
- Identify which system made a decision
- Attribute responsibility to specific agents
- Claim authority for any judgment
- Assert design intent

**It ONLY**:
- Records what happened
- Preserves artifacts
- Maintains temporal order
- Provides verifiable evidence

---

## Why This Matters

### Legal Clarity

Evidence that attributes decisions becomes a claim.
Claims require defense.
This repository makes no claims.

### Audit Fitness

Auditors need facts, not interpretations.
Attribution implies interpretation of cause.
This repository provides observable state only.

### System Neutrality

Multiple systems may use the same evidence format.
Attribution would tie evidence to a specific system.
This repository remains system-agnostic.

---

## Boundary Between Evidence and Design

**Evidence Repository** (this repo):
- "STOP event occurred at timestamp T"
- "Rule ID: R42 triggered"
- "Human decision: Abort"
- "Execution halted"

**Design Repository** (external):
- "System X implements STOP rules"
- "Agent Y has authority to trigger R42"
- "Rule R42 is part of safety boundary"
- "System architecture diagram"

**The Separation**:
```
Evidence → "What happened" (no subject)
Design   → "Who/what designed it" (has subject)
```

---

## Enforcement

This policy is enforced through:

1. **Template Structure**: Incident logs have no attribution fields
2. **Review Process**: PRs with attribution claims are rejected
3. **Documentation**: All docs use passive voice ("was triggered" not "X triggered")
4. **CI Notice**: Automated reminder on every push

---

## Exception: Artifact Metadata

**File metadata** (timestamps, hashes, sizes) is preserved.

**This is NOT attribution**:
```json
{
  "file": "incident_001_screenshot.png",
  "size": 42KB,
  "hash": "abc123...",
  "timestamp": "2026-01-05T12:00:00Z"
}
```

**This WOULD BE attribution (not allowed)**:
```json
{
  "file": "incident_001_screenshot.png",
  "created_by": "Echo System",        ← NO
  "decision_maker": "Agent Alpha",    ← NO
  "authority": "STOP Boundary v2.1"   ← NO
}
```

---

## Citation

When citing evidence from this repository, do not attribute decisions:

**Correct**:
> "Incident Log 001 shows a STOP event at 14:32:11 UTC."

**Incorrect**:
> "The Echo system stopped execution at 14:32:11 UTC."

**Why**: The second adds attribution not present in the evidence.

---

## Relationship to Constitution Repos

**Constitution repositories** DO attribute:
- Design authority
- Rule ownership
- System architecture

**This repository** does NOT attribute:
- Who decided
- Why it was decided
- What should have been decided

**The connection**: Constitution defines rules, Evidence records their execution.

**No reverse attribution**: Evidence cannot prove "system X made this decision" - only that "this decision occurred."

---

## Final Principle

**Evidence is silent on intent.**

**Attribution implies intent.**

**This repository remains silent.**

---

**Last Updated**: 2026-01-05
**Policy Version**: 1.0.0
**Status**: Active
