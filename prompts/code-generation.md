# Code Generation

## Objective

Implement the requested functionality in the existing codebase while
preserving established architecture, coding conventions, and behavior.

## Task

[DESCRIBE THE FUNCTIONALITY TO IMPLEMENT]

## Requirements

- Review the existing codebase before making changes.
- Identify the relevant modules, dependencies, interfaces, and conventions.
- Determine whether existing functionality can be extended instead of
  introducing duplicate implementations.
- Follow the project's established architecture and style.
- Implement the smallest complete solution that satisfies the requirements.
- Preserve backward compatibility unless explicitly instructed otherwise.
- Validate external input and handle expected failure conditions.
- Avoid unnecessary dependencies, abstractions, configuration, and files.
- Do not introduce placeholders, stubs, or incomplete implementations
  unless explicitly requested.
- Do not silently change unrelated functionality.
- Never invent APIs, configuration options, dependency behavior, or
  project requirements. Inspect available source code and documentation.

## Constraints

- Target platform: [PLATFORM OR RUNTIME]
- Language and version: [LANGUAGE AND VERSION]
- Frameworks: [FRAMEWORKS]
- Compatibility requirements: [COMPATIBILITY REQUIREMENTS]
- Additional constraints: [CONSTRAINTS]

If a value is unspecified, inspect the repository and use its established
configuration. Ask a clarifying question only when an unresolved ambiguity
materially affects correctness, security, or architecture.

## Workflow

1. Inspect repository instructions, relevant source files, configuration,
   dependency manifests, and existing tests.
2. Summarize the intended implementation and identify significant risks.
3. Determine the appropriate files and interfaces to modify.
4. Implement the functionality using existing project conventions.
5. Add or update tests covering normal behavior, edge cases, and failures.
6. Run the relevant tests, linters, formatters, and type checks available
   in the project.
7. Inspect the final diff for unrelated changes, regressions, and omissions.

## Quality Requirements

- Prefer readable, maintainable code over clever or unnecessarily complex
  solutions.
- Use descriptive names, explicit interfaces, and appropriate type hints
  or types where the project supports them.
- Keep responsibilities cohesive and avoid unnecessary coupling.
- Handle errors explicitly and provide actionable error information.
- Protect secrets and sensitive data.
- Do not weaken validation, security controls, or tests to make an
  implementation pass.
- Do not claim that a check passed unless it was actually executed and
  its result was observed.
- If verification cannot be completed, explain why and identify what
  remains unverified.

## Completion Report

Provide:

1. Summary of the implementation.
2. Files created or modified and the purpose of each change.
3. Important design decisions and assumptions.
4. Tests and validation commands executed, including their results.
5. Known limitations, outstanding issues, and recommended follow-up work.