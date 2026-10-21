# Testing

## Objective

Create or improve a reliable test suite that verifies expected behavior,
covers meaningful edge cases, detects regressions, and produces
reproducible results.

## Testing Scope

- Feature or component: [TARGET]
- Expected behavior: [REQUIREMENTS]
- Test types: [UNIT, INTEGRATION, API, END-TO-END, OR OTHER]
- Framework: [TEST FRAMEWORK]
- Coverage goals: [OPTIONAL GOALS]
- Constraints: [ENVIRONMENT AND DEPENDENCIES]

## Principles

- Inspect existing tests and follow established testing conventions.
- Derive assertions from requirements and observable behavior.
- Prefer deterministic tests with explicit setup and cleanup.
- Use realistic fixtures and minimal test data.
- Test public contracts rather than implementation details unless
  implementation-level testing is necessary.
- Avoid unnecessary mocks that conceal integration failures.
- Do not weaken assertions or delete valid tests to obtain a passing suite.
- Do not change production code merely to accommodate a flawed test.
- Keep tests isolated from production systems and real user data.
- Never claim tests passed without executing them and observing the result.

## Workflow

1. Inspect repository guidance, test configuration, existing fixtures,
   and the code under test.
2. Identify normal cases, boundary conditions, invalid inputs, failure
   modes, and important state transitions.
3. Map each significant requirement to one or more assertions.
4. Select appropriate test levels and avoid duplicating coverage without
   a clear benefit.
5. Implement tests using the project's existing framework and conventions.
6. Verify that tests fail when the intended behavior is deliberately
   absent or incorrect, when practical.
7. Run the focused tests and then the relevant broader suite.
8. Run applicable type checks, linters, and coverage tools.
9. Investigate failures and distinguish test defects from product defects.
10. Review test isolation, determinism, execution time, and cleanup.

## Coverage Considerations

When relevant, include tests for:

- Expected successful behavior.
- Empty, missing, malformed, and boundary inputs.
- Invalid states and rejected operations.
- Exceptions, timeouts, and dependency failures.
- Authorization and access-control boundaries.
- Data persistence, serialization, and migrations.
- Concurrency and repeated operations.
- Resource cleanup and rollback behavior.
- Regression cases for previously reported defects.
- Compatibility across supported runtimes or platforms.

Do not pursue a numeric coverage target at the expense of meaningful
assertions. Coverage percentage alone does not demonstrate correctness.

## Test Environment Safety

- Use isolated databases, temporary directories, and controlled fixtures.
- Stub external services when appropriate.
- Do not use production credentials or modify production data.
- Make destructive integration tests opt-in and explicitly documented.
- Ensure cleanup runs even when a test fails.
- Never silently skip tests that are required for the task.

## Completion Report

### Test Coverage
Describe the behaviors and failure modes covered.

### Files Changed
List test files and any production files modified.

### Execution Results
For each executed command, report the observed result, including failures
and skipped tests.

### Coverage and Gaps
Include coverage metrics if actually measured and explain meaningful gaps.

### Follow-up
Identify additional tests or environments needed to increase confidence.