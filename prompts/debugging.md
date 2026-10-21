# Debugging

## Objective

Identify the root cause of a reported defect, establish the evidence supporting that diagnosis, and implement or recommend the smallest reliable fix.

## Problem Description

- Expected behavior: [EXPECTED BEHAVIOR]
- Actual behavior: [OBSERVED BEHAVIOR]
- Error message or logs: [ERRORS AND LOGS]
- Reproduction steps: [REPRODUCTION STEPS]
- Environment: [OS, RUNTIME, VERSIONS, AND CONFIGURATION]
- Recent changes: [RELEVANT CHANGES]

## Diagnostic Principles

- Distinguish symptoms from root causes.
- Base conclusions on evidence, not assumptions.
- Reproduce the problem when practical.
- Prefer targeted diagnostics over broad, disruptive changes.
- Preserve existing behavior unrelated to the defect.
- Avoid suppressing exceptions, disabling validation, or weakening tests merely to make the error disappear.
- Do not perform destructive operations or alter production systems without explicit authorization.
- Protect secrets and personal information in logs and diagnostic output.

## Workflow

1. Inspect repository instructions, relevant code, configuration, dependency versions, and existing tests.
2. Translate the report into a specific, observable failure condition.
3. Reproduce the issue using the safest available method.
4. Trace the execution path from the failing behavior to its source.
5. Develop plausible hypotheses and rank them by supporting evidence.
6. Use targeted logging, assertions, tests, or diagnostic commands to distinguish competing hypotheses.
7. Identify the underlying cause and explain the causal chain.
8. Implement the smallest appropriate fix, if authorized.
9. Add a regression test that fails before the fix and passes afterward, where feasible.
10. Run the relevant regression tests and nearby affected tests.
11. Inspect the diff for unintended behavior changes.

## Diagnostic Constraints

- Do not change multiple unrelated variables at once.
- Do not update dependencies speculatively as a first response.
- Do not assume a reported correlation establishes causation.
- Do not remove failing tests or broadly relax assertions.
- Do not fabricate command output, logs, stack traces, or test results.
- If the issue cannot be reproduced, document the attempts and remaining hypotheses rather than presenting an unverified diagnosis as fact.
- If a fix requires unavailable infrastructure, credentials, or external services, clearly identify the limitation.

## Completion Report

### Symptom
Describe the observed failure and expected behavior.

### Root Cause
Explain the cause and supporting evidence. If unconfirmed, label it as the leading hypothesis rather than a proven root cause.

### Resolution
Describe the fix and why it addresses the underlying problem.

### Changes
List modified files and their purpose.

### Verification
Include reproduction steps, tests, commands, and observed results.

### Remaining Risks
Identify unresolved hypotheses, environmental dependencies, or follow-up work.