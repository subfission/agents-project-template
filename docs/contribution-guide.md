# Contribution Guide

Thank you for helping improve this collection of prompts, skills, and templates for AI-assisted development.

Contributions should make resources more useful, reliable, secure, and maintainable for developers working with different repositories and AI agents.

## Ways to Contribute

Contributions may include:

- Adding a prompt for a well-defined development workflow.
- Improving an existing prompt's clarity, safety, or verification steps.
- Adding or refining reusable skill definitions.
- Adding templates for repository files, agent configuration, documentation, or workflows.
- Providing realistic examples and usage instructions.
- Correcting inaccurate instructions, broken links, or outdated references.
- Documenting agent-specific compatibility and limitations.
- Consolidating redundant resources or removing misleading content.

Before creating a new resource, search the repository for an existing one that could be improved or extended.

## Before You Start

1. Read `README.md` to understand the repository's organization and scope.
2. Read `docs/authoring-guidelines.md` for content and quality expectations.
3. Read `docs/agent-compatibility.md` if your contribution targets a particular agent or skill format.
4. Inspect related resources to avoid duplication and preserve consistent terminology.
5. For substantial changes, open an issue or discuss the proposal with maintainers before investing in a large implementation, if the project uses an issue workflow.

Follow any additional repository-specific contribution instructions.

## Directory Conventions

Use the existing layout where possible:

- `prompts/`: task-oriented prompts grouped by development workflow.
- `skills/`: reusable agent capabilities and procedures.
- `templates/`: reusable files, configurations, and document structures.
- `examples/`: illustrative implementations and usage examples.
- `docs/`: repository-wide authoring, compatibility, and contribution guidance.

Use lowercase kebab-case for new filenames unless a target ecosystem requires a different convention. Keep each resource in the most appropriate location.

## Requirements for New Prompts

A prompt should:

- Have a clear title and objective.
- Identify required inputs and use explicit placeholders for information that must be supplied.
- Define scope, constraints, and expected outcomes.
- Instruct repository-aware agents to inspect relevant context before acting.
- Avoid unnecessary assumptions about language, framework, platform, or agent.
- Include appropriate safety and security boundaries.
- Explain how to validate the result.
- Require accurate reporting of checks performed and remaining limitations.
- Avoid conflicting, redundant, or vague instructions.
- Be usable without relying on hidden conversation history.

Use the structure described in `docs/authoring-guidelines.md` as a guide, not as a rigid requirement. Include only sections that add value for the specific task.

## Requirements for Skills and Templates

For skills:

- Follow the target agent's current format and metadata requirements.
- Clearly state the skill's purpose, scope, and expected behavior.
- Document required tools, permissions, and external dependencies.
- Keep supporting references organized and relevant.
- Avoid claiming compatibility that has not been verified.

For templates:

- Make placeholders recognizable and explain how to populate them.
- Use safe example values rather than real credentials or personal data.
- Identify required and optional fields.
- Preserve the syntax required by the target file format.
- Include usage guidance when the intended purpose is not obvious.

## Quality and Safety Standards

All contributions should:

- Be focused and reasonably sized.
- Preserve unrelated files and behavior.
- Use clear, professional language.
- Avoid including secrets, access tokens, private keys, internal customer data, or other sensitive information.
- Avoid instructions that exceed the user's authorized scope.
- Avoid destructive actions unless the resource explicitly requires them and includes appropriate safeguards.
- Never instruct agents to conceal failures, bypass required security controls, or misrepresent verification results.
- Clearly distinguish verified facts from assumptions and examples.

Do not add fabricated tool output, test results, benchmarks, compatibility claims, or security findings.

## Testing Your Contribution

Before submitting:

1. Check the Markdown formatting and heading hierarchy.
2. Verify internal links and referenced repository paths.
3. Confirm that examples are syntactically plausible and safe to copy.
4. Check that placeholders and defaults are understandable.
5. Compare the resource with related prompts, skills, and templates.
6. Run relevant validation commands or examples when feasible.
7. Record what was tested and what remains unverified.

If a prompt or template is designed for a specific agent, test it with that agent when possible. If you cannot test it, say so rather than implying compatibility.

## Pull Request or Change Description

Describe the contribution clearly. Include:

- **Purpose:** What problem does the change solve?
- **Changes:** Which resources were added, updated, consolidated, or removed?
- **Rationale:** Why is the proposed approach appropriate?
- **Validation:** What checks or examples were executed?
- **Compatibility:** Which agents, runtimes, or formats are affected?
- **Limitations:** What remains untested or unresolved?

For small corrections, a concise description is sufficient. For broad changes, explain the design and migration implications.

## Review Expectations

Reviewers may evaluate:

- Relevance and uniqueness of the resource.
- Clarity of instructions and placeholders.
- Alignment with repository conventions.
- Technical accuracy and practical usability.
- Appropriate safety and security boundaries.
- Evidence supporting compatibility and verification claims.
- Long-term maintenance cost and overlap with existing resources.

Feedback should focus on concrete improvements. Contributors should address substantive concerns or explain why a different approach is warranted.

## Versioning and Maintenance

When an existing resource changes materially:

- Update related examples and documentation.
- Check references to the resource elsewhere in the repository.
- Note breaking changes to placeholders, output formats, or expected behavior.
- Preserve backward compatibility where practical.
- Explain any necessary migration steps.

Avoid adding version numbers to individual resources unless versioning is needed for a specific integration or release process.

## License and Attribution

Contributions must be compatible with the repository's license and any applicable third-party licenses. Attribute external material where required, and do not copy proprietary prompts, confidential instructions, or copyrighted content without authorization.

If the repository has no license yet, consult the maintainer before adding material with unclear licensing terms.

## Final Checklist

- [ ] The contribution addresses a clear need.
- [ ] Related resources were checked for duplication.
- [ ] Files follow the repository's directory and naming conventions.
- [ ] Instructions and placeholders are clear.
- [ ] Examples contain no real secrets or sensitive information.
- [ ] Safety and authorization boundaries are appropriate.
- [ ] Links and referenced paths were checked.
- [ ] Validation results are reported honestly.
- [ ] Related documentation was updated where necessary.
- [ ] Compatibility claims are supported by evidence or clearly labeled as untested.

Thank you for helping make the toolkit more useful and dependable.
