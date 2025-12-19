# Postmortem [ID]

**Postmortem ID**: [Same as incident ID: 001, 002, ...]

**Incident Reference**: INCIDENT_LOG_[ID].md

**Created**: [ISO 8601 timestamp]

**Boundary Violation Type**: [stop_rule_bypassed | classifier_failed | unexpected_execution | other]

---

## Postmortem Creation Criteria

**This postmortem exists because** (check all that apply):
- [ ] STOP boundary was bypassed (execution reached unsafe state)
- [ ] Classifier assigned wrong category (action misclassified)
- [ ] Telemetry revealed statistical anomaly (unexpected pattern)
- [ ] Other boundary violation: [specify]

**If none checked above, this postmortem should not exist.**

---

## Incident Summary

**What Was Attempted**: [Brief description from incident log]

**What Actually Happened**: [Factual description of execution]

**What Should Have Happened**: [Expected behavior per STOP rules]

**Discrepancy**: [Difference between expected and actual]

---

## Boundary Violation Description

**Which Boundary**: [Specific STOP rule or principle from Constitution]

**How Violated**: [Mechanism of violation - code bug, rule gap, logic error]

**Violation Evidence**:
```
[Code snippet, log output, or artifact showing violation]
```

---

## Evidence Chain

**Reconstruction Timeline**:

1. **[Timestamp]**: [System state before incident]
2. **[Timestamp]**: [Action initiated]
3. **[Timestamp]**: [STOP check occurred (or didn't)]
4. **[Timestamp]**: [Execution proceeded (should have stopped)]
5. **[Timestamp]**: [Result observed]

**Artifacts Used**:
- [List all artifacts examined]
- [Screenshots, logs, reports referenced]

---

## System State

### Before Incident

**Execution Context**:
```
[CWD, environment, page URL, etc.]
```

**Active Rules**:
- [List STOP rules that were active]

**Expected Behavior**:
- [What should have triggered based on rules]

---

### After Incident

**Resulting State**:
```
[System state after execution]
```

**Changes**:
- [Files modified, pages navigated, commands run]

**Boundary Status**:
- [Which boundaries were crossed]

---

## Root Cause

**Direct Cause**: [Immediate technical reason for violation]

**Example**:
- Code: `if action == 'delete'` (typo: should be `'delete_file'`)
- Result: Rule check skipped for `delete_file` action

**Contributing Factors** (factual only):
- [Environmental condition 1]
- [Code state 1]
- [Configuration 1]

**DO NOT INCLUDE**:
- "We should have..." (recommendation)
- "This happened because we didn't..." (judgment)
- "In the future..." (prescription)

---

## Verification

**How Violation Was Detected**:
- [ ] Telemetry analysis
- [ ] Manual execution review
- [ ] Artifact inspection
- [ ] Other: [specify]

**Detection Timestamp**: [When violation was noticed]

**Detection Method**: [Automated scan | Manual review | User report]

---

## Scope of Impact

**Actions Affected**: [Which action types were vulnerable]

**Incidents Affected**: [List incident IDs with same root cause]

**Temporal Scope**: [Time period during which violation was possible]

**Domain Scope**: [web | local | both | other]

---

## Evidence of Fix (If Applied)

**Fix Applied**: [Yes | No | N/A]

**Fix Description** (factual only):
```
[Code change, rule update, configuration change]
```

**Fix Verification**:
```
[Test result, re-execution outcome, proof of boundary restored]
```

**Boundary Constitution Update**: [Link to commit/tag if rules changed]

---

## Related Incidents

**Same Root Cause**:
- INCIDENT_[ID]
- INCIDENT_[ID]

**Similar Pattern**:
- INCIDENT_[ID]
- INCIDENT_[ID]

**Sequence**:
- [If part of cascade, list incident sequence]

---

## Boundary Layer Analysis

**Layer Violated**: [Human Authority | Judgment Boundary | Execution Domain | Evidence]

**Enforcement Mechanism Failed**: [State-based check | Blocking input | Code-based rule | Other]

**Structural vs Behavioral**: [Was this a code bug or prompt misinterpretation?]

---

## No Recommendations Section

**This postmortem does NOT contain**:
- Recommendations for fixes
- Design improvements
- "Lessons learned"
- Future action items

**Reason**: Postmortems are descriptive (what happened), not prescriptive (what to do).

**Where Recommendations Belong**: Boundary Constitution repo (design decisions), not Evidence repo (facts).

---

## Attestation

**This postmortem contains**:
- ✅ Facts only (what happened)
- ✅ Evidence references (artifacts)
- ✅ Timeline reconstruction
- ✅ Root cause identification

**This postmortem does NOT contain**:
- ❌ Judgments (whether violation was "bad")
- ❌ Recommendations (what to change)
- ❌ Blame assignment (who caused it)
- ❌ Speculation (what might happen)

---

## Metadata

**Analyst**: [human | automated_analysis]

**Analysis Duration**: [Time spent reconstructing]

**Confidence Level**: [high | medium | low]

**Confidence Basis**: [Artifact completeness, reproduction success, etc.]

---

## Template Version

**Version**: 1.0

**Last Updated**: 2025-12-20

---

## Immutability Notice

**This postmortem is locked upon creation.**

If errors are found:
- Create new postmortem with correction
- Reference original postmortem ID
- Do NOT edit this file

**Evidence integrity requires immutability.**
