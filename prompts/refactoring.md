# Refactoring

## Objective

Improve the internal structure, readability, maintainability, or performance characteristics of existing code while preserving its externally observable behavior unless an intentional behavior change is explicitly requested.

## Refactoring Goal

[DESCRIBE THE CODE TO REFACTOR AND THE DESIRED OUTCOME]

## Scope and Constraints

- Target files or modules: [TARGETS]
- Primary goal: [MAINTAINABILITY, SIMPLICITY, PERFORMANCE, OR OTHER]
- Compatibility requirements: [REQUIREMENTS]
- Allowed behavior changes: [NONE OR EXPLICITLY LISTED]
- Additional constraints: [CONSTRAINTS]

## Core Principles

- Establish the existing behavior before changing implementation.
- Prefer incremental, reviewable changes.
- Preserve public interfaces, data formats, and established contracts.
- Follow existing architecture unless changing it is part of the task.
- Avoid unrelated cleanup, formatting churn, and opportunistic rewrites.
- Do not introduce abstractions without a concrete benefit.
- Do not optimize performance without evidence or a stated requirement.
- Do not remove seemingly unused code without checking its references, dynamic usage, integrations, and external consumers.
- Do not change dependency versions unless explicitly required.

## Workflow

1. Inspect repository instructions, target code, callers, dependencies, and existing tests.
2. Identify structural problems and explain the expected benefits of addressing them.
3. Establish a baseline using existing tests and relevant checks.
4. Determine which externally observable behaviors must remain unchanged.
5. Design the smallest coherent set of structural changes.
6. Refactor in logical increments, keeping changes easy to review.
7. Update imports, interfaces, types, and internal documentation as needed.
8. Add or adjust tests where the current suite does not adequately protect behavior.
9. Run relevant tests, static analysis, type checking, and formatting.
10. Review the diff for unintended semantic changes and unnecessary edits.

## Refactoring Guidelines

Prefer, where appropriate:

- Smaller functions with cohesive responsibilities.
- Clear separation between business logic and infrastructure.
- Reduced duplication when a shared abstraction genuinely improves clarity.
- Explicit dependencies and predictable side effects.
- Consistent error handling and resource management.
- Strong typing and clear interfaces.
- Simpler control flow and removal of dead code when verified.

Avoid:

- Large-scale rewrites when incremental changes suffice.
- Generic frameworks for isolated problems.
- Premature abstraction or unnecessary design patterns.
- Changing behavior under the guise of structural cleanup.
- Hiding errors or relaxing correctness checks.
- Removing tests solely because implementation details changed.

## Validation Requirements

- Run baseline checks before refactoring when feasible.
- Compare behavior before and after changes using tests or other evidence.
- Add regression tests for important existing behavior that lacks coverage.
- Report any unavailable or failing checks accurately.
- If behavior changes are explicitly authorized, enumerate them separately from behavior-preserving changes.

## Completion Report

1. Refactoring objective and outcome.
2. Files changed and the structural improvements made.
3. Observable behavior preserved and any intentional changes.
4. Tests and validation results.
5. Remaining risks, trade-offs, and possible follow-up work.