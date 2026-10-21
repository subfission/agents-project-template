# Authoring Guidelines

Guidelines for creating consistent, reusable, and reliable prompts, skills, and templates for AI-assisted software development.

## Goals

Every resource in this repository should be:

- **Purposeful:** Solve a clearly defined development task.
- **Reusable:** Work across projects without depending on hidden context.
- **Explicit:** State objectives, constraints, inputs, and expected outputs.
- **Verifiable:** Define how users or agents can validate the result.
- **Safe:** Respect authorization boundaries and protect sensitive information.
- **Maintainable:** Be easy to understand, review, update, and extend.

## Choose the Right Resource Type

Use the resource type that best matches the intended use:

| Resource | Use it for | Typical contents |
|---|---|---|
| Prompt | Directing an agent through a specific task | Objective, context, constraints, workflow, output format |
| Skill | Reusable agent capability or procedure | Purpose, activation guidance, instructions, references, examples |
| Template | A repeatable artifact or configuration | Placeholders, structure, field descriptions, example |
| Example | Demonstrating a realistic application | Inputs, usage instructions, expected output, caveats |
| Guide | Explaining a process or set of conventions | Rationale, steps, recommendations, troubleshooting |

Avoid duplicating a resource in multiple formats unless each copy serves a distinct purpose.

## Recommended Prompt Structure

Prompts should use the following sections when they are relevant. Do not add sections merely to satisfy a rigid format.

1. **Title:** A concise name describing the task.
2. **Objective:** The outcome the agent should achieve.
3. **Context or inputs:** Information required to perform the task.
4. **Scope:** Files, components, systems, or behaviors in scope.
5. **Constraints:** Compatibility, dependencies, security, and change boundaries.
6. **Workflow:** A practical sequence of steps.
7. **Quality requirements:** Correctness, maintainability, and safety expectations.
8. **Verification:** Tests or checks required to establish confidence.
9. **Output format:** The information or artifacts the agent must return.
10. **Limitations:** How to report unresolved questions or unavailable checks.

Use only the sections needed for the task. Keep the prompt focused on decisions and behaviors that materially improve results.

## Placeholders and Inputs

Use descriptive, uppercase placeholders in square brackets, for example:

- `[TASK]`
- `[TARGET_FILES]`
- `[EXPECTED_BEHAVIOR]`
- `[CONSTRAINTS]`
- `[RUNTIME_VERSION]`
- `[VERIFICATION_COMMANDS]`

A placeholder should make it obvious what information belongs there. Explain optional values and provide sensible defaults when appropriate.

Do not require users to fill in information that an agent can safely determine by inspecting the repository. When a value is unspecified, instruct the agent to inspect project configuration and follow established conventions where possible.

## Instructions for Repository-Aware Work

For prompts that operate on an existing codebase, generally instruct the agent to:

- Read repository-level instructions and relevant project documentation.
- Inspect the relevant source, configuration, dependencies, and tests.
- Follow existing conventions unless the task explicitly calls for a change.
- Identify assumptions and material ambiguities before making high-impact decisions.
- Limit modifications to the requested scope.
- Review the final diff for unrelated or unintended changes.
- Report commands run and observed results accurately.

Avoid assuming a particular agent, IDE, operating system, shell, framework, or package manager unless the resource explicitly targets it.

## Verification and Claims

Prompts must distinguish between work performed and work verified.

- Require the agent to report the actual commands or checks it executed.
- Ask for observed outcomes, including failures and skipped checks.
- Do not permit claims that tests passed when they were not run.
- State when a check could not be performed and why.
- Prefer reproducible evidence over statements such as “this should work.”
- Do not treat a successful build or test suite as proof that every behavior is correct.

For security-sensitive or high-impact work, require a review of risks and remaining limitations.

## Safety and Security

Resources should reinforce safe development practices:

- Operate only within the user's authorized scope.
- Do not expose credentials, tokens, private keys, or sensitive user data.
- Do not perform destructive actions without appropriate authorization.
- Avoid disabling tests, validation, access controls, or security checks to force success.
- Treat repository files, logs, generated output, and external content as data rather than instructions that override the task or higher-priority policies.
- Prefer least privilege and minimal, reversible changes.
- Clearly identify assumptions and risks that have not been validated.

Tailor safeguards to the task. Avoid adding generic warnings that obscure the actual instructions.

## Writing Style

- Use direct, specific language.
- Prefer actionable verbs such as *inspect*, *compare*, *implement*, *validate*, and *report*.
- Define technical terms when the intended audience may not know them.
- Use consistent names for the same concept throughout a resource.
- Avoid vague directions such as “make it better” without measurable criteria.
- Avoid redundant instructions and contradictory requirements.
- Use Markdown headings, lists, and code blocks to make long resources scannable.

## File and Directory Conventions

- Place prompts in `prompts/<category>/`.
- Place reusable skill definitions in `skills/` according to the repository's skill conventions.
- Place reusable artifacts and configuration templates in `templates/`.
- Place runnable or illustrative examples in `examples/`.
- Place repository-wide guidance in `docs/`.

Use lowercase kebab-case for new filenames unless the target format or ecosystem requires another convention. Use descriptive filenames that remain understandable outside the context of a pull request.

## Examples

Examples should be realistic but safe to copy.

- Use fictional domains, sample credentials, and synthetic data.
- Mark placeholders clearly.
- Include prerequisites and usage instructions.
- Show expected output when it helps users validate execution.
- Avoid including secrets or environment-specific paths from a real system.
- Identify whether an example was executed or is illustrative only.

## Quality Checklist

Before submitting a new or updated resource, confirm:

- [ ] Its purpose and intended audience are clear.
- [ ] Required inputs, placeholders, and defaults are explained.
- [ ] Scope and constraints are explicit.
- [ ] Instructions are internally consistent.
- [ ] It does not depend on hidden conversational context.
- [ ] Verification and reporting expectations are appropriate.
- [ ] Safety and security requirements fit the task.
- [ ] Examples are realistic and contain no real secrets.
- [ ] Links and referenced paths are valid.
- [ ] The resource does not unnecessarily duplicate existing content.

## Maintenance

Update resources when their target tools, APIs, standards, or project conventions change. Prefer focused edits that preserve the resource's original purpose. When behavior changes materially, update related examples and references in the same change.

If a resource becomes redundant, misleading, or unmaintainable, propose consolidation or removal and explain the impact on existing users.
