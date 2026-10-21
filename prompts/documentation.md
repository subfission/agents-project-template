# Documentation

## Objective

Create or update accurate, usable, and maintainable documentation that reflects the actual behavior of the software and helps the intended audience accomplish specific tasks.

## Documentation Task

- Target: [FILES, MODULES, FEATURES, OR PROJECT]
- Document type: [README, API REFERENCE, GUIDE, RUNBOOK, OR OTHER]
- Audience: [DEVELOPERS, OPERATORS, USERS, OR CONTRIBUTORS]
- Desired outcome: [DOCUMENTATION GOAL]
- Output location: [PATH OR EXISTING CONVENTION]

## Source of Truth

Use evidence in the following order, as applicable:

1. Executable source code and defined interfaces.
2. Automated tests and verified runtime behavior.
3. Configuration files, dependency manifests, and schemas.
4. Existing authoritative project documentation.
5. Explicit requirements and maintainer-provided specifications.

If sources conflict, identify the discrepancy instead of silently choosing an unsupported interpretation.

Do not invent commands, APIs, environment variables, defaults, output, compatibility claims, or supported features.

## Workflow

1. Inspect repository instructions, project structure, and existing docs.
2. Identify the intended reader and the task the documentation should help them complete.
3. Verify relevant behavior against source code, configuration, tests, or safe execution where feasible.
4. Follow existing documentation conventions and terminology.
5. Draft or update the smallest set of documents needed.
6. Include practical examples that reflect actual interfaces and behavior.
7. Verify command syntax, paths, option names, configuration keys, code samples, and internal links where feasible.
8. Check consistency with related documentation.
9. Review the result for ambiguity, outdated statements, omissions, and unnecessary duplication.

## Content Requirements

Include applicable information such as:

- Purpose, scope, and intended audience.
- Prerequisites and supported environments.
- Installation and setup instructions.
- Configuration options, defaults, and required values.
- Usage examples and expected outcomes.
- API contracts, parameters, return values, and errors.
- Architecture and important design decisions.
- Testing and development workflows.
- Troubleshooting and common failure modes.
- Security considerations and handling of sensitive information.
- Known limitations, compatibility requirements, and migration notes.
- Links to authoritative references and related project documents.

For README files, prioritize a concise overview, prerequisites, quick start, core usage, configuration, testing, and links to deeper documentation.

For API references, document actual contracts, validation behavior, authentication requirements, response formats, and error semantics.

For runbooks, provide explicit prerequisites, safe execution steps, verification, rollback procedures, and escalation criteria where relevant.

## Writing Standards

- Use clear, direct language appropriate to the audience.
- Prefer actionable instructions over vague descriptions.
- Use consistent terminology and formatting.
- Keep examples minimal, complete, and reproducible.
- Mark placeholders explicitly.
- Distinguish required configuration from optional configuration.
- Never include real secrets, credentials, or sensitive personal data.
- Avoid duplicating information that belongs in an authoritative source.
- Do not claim a command or example was tested unless it was executed.
- Label assumptions, unverified behavior, and environment-specific steps.

## Scope and Change Control

- Preserve unrelated documentation.
- Do not modify application behavior solely to match inaccurate docs unless code changes are explicitly requested.
- If implementation and documentation disagree, report the discrepancy and recommend the appropriate correction.
- Do not create new documentation files when an existing document is the natural location, unless a separate document materially improves navigation or maintainability.

## Validation

Where applicable:

- Execute documented commands in a safe environment.
- Validate code examples, configuration snippets, and API examples.
- Check relative links and referenced file paths.
- Compare documented options against actual CLI help or schemas.
- Verify that setup instructions match the dependency manifests.
- Ensure generated or copied examples do not disclose sensitive data.

If validation is not possible, state what remains unverified.

## Completion Report

1. Documents created or updated.
2. Audience and purpose of the changes.
3. Important facts verified against the implementation.
4. Commands, links, and examples checked.
5. Known discrepancies, assumptions, and remaining documentation gaps.