# AI Agents & Project Developer Toolkit

A curated collection of prompt templates, agent skill-building templates, and reusable development resources for engineers using AI agents to build, test, secure, and maintain software.

This repository provides a structured foundation for integrating AI agents into software development workflows. It emphasizes reusable patterns, consistent instructions, tool-agnostic design, and durable documentation so that developers can apply the same practices across different projects, agents, and harnesses.

## Objectives

- **Standardize AI-assisted development:** Establish repeatable workflows for common engineering tasks.
- **Improve agent reliability:** Provide clear instructions, constraints, acceptance criteria, and validation requirements.
- **Support multiple agents and harnesses:** Encourage portable templates that work across IDE assistants, CLI agents, autonomous coding systems, and custom agent implementations.
- **Build reusable skills:** Provide templates for creating, documenting, testing, and maintaining agent skills.
- **Preserve project knowledge:** Help developers capture architecture, conventions, decisions, and operational requirements in durable repository artifacts.
- **Promote secure development:** Incorporate security reviews, least-privilege principles, secret handling, and independent verification.
- **Reduce prompt duplication:** Encourage modular templates that can be adapted and reused rather than rewritten for every project.

## Repository Contents

The repository is organized by purpose. The directory structure may evolve as new templates and workflows are introduced.

```text
.
├── README.md
├── prompts/
│   ├── project-bootstrap.md
│   ├── code-generation.md
│   ├── code-review.md
│   ├── debugging.md
│   ├── refactoring.md
│   ├── testing.md
│   ├── security.md
│   └── documentation.md
├── skills/
│   ├── templates/
│   ├── examples/
│   └── development/
├── templates/
│   ├── agents/
│   ├── repository/
│   ├── documentation/
│   ├── configuration/
│   └── workflows/
├── examples/
└── docs/
    ├── authoring-guidelines.md
    ├── agent-compatibility.md
    └── contribution-guide.md
```

The tree illustrates the intended organization; individual directories may be added as their contents become available.

### `prompts/` - Reusable Prompt Templates

Prompts for directing AI agents through defined engineering tasks.

Potential categories include:

| Category | Purpose |
|---|---|
| Project bootstrap | Establish repository structure, instructions, documentation, and development tooling. |
| Code generation | Implement features according to existing architecture and conventions. |
| Code review | Identify defects, maintainability issues, security risks, and regressions. |
| Debugging | Investigate failures systematically and develop verified fixes. |
| Refactoring | Improve internal design while preserving intended behavior. |
| Testing | Generate tests, improve coverage, and validate edge cases. |
| Security | Review application security, dependencies, configurations, and trust boundaries. |
| Documentation | Create or maintain technical documentation and operational runbooks. |

Prompts should define the agent's role, objective, available context, constraints, interaction requirements, expected deliverables, and validation criteria.

### `skills/` - Agent Skill Development

Templates and examples for building reusable agent skills.

A skill should define a specific capability, when it should be used, its prerequisites, its execution procedure, and how its results are validated.

This directory may include:

- Skill authoring templates.
- Skill metadata and directory structure examples.
- Task-specific procedures.
- Reference documentation patterns.
- Supporting script conventions.
- Skill testing and validation checklists.
- Portability guidance for different agent harnesses.

Where possible, skills should follow established formats such as the [Agent Skills specification](https://agentskills.io/specification), with harness-specific adaptations where necessary.

### `templates/` — Developer and Repository Templates

Reusable artifacts that can be incorporated into individual projects.

Examples include:

- `AGENTS.md` and other agent instruction templates.
- Repository `README.md` templates.
- Architecture documentation.
- Architecture Decision Records (ADRs).
- Development and testing guides.
- Security policies and review checklists.
- Issue and pull request templates.
- Development task and release checklists.
- Configuration schemas and environment templates.
- CI workflow examples.
- Agent compatibility and integration documentation.

Templates should be adaptable to a project's language, framework, security requirements, and development process rather than assuming a universal technology stack.

### `examples/` — Reference Implementations

Examples demonstrating how prompts, skills, and repository templates can be combined into practical development workflows.

Examples should clearly distinguish illustrative configurations from tested, production-ready implementations.

### `docs/` — Authoring and Usage Guidance

Documentation describing how to select, customize, validate, and maintain the resources in this repository.

It should also document supported conventions, compatibility limitations, and contribution expectations.

## Design Principles

### 1. Agent and harness portability

Prefer tool-agnostic instructions and standard formats over assumptions about a particular agent.

When an agent requires its own configuration, keep that configuration as a thin adapter to shared project instructions. Verify the supported file names, formats, and discovery behavior of each target harness.

### 2. Explicit instructions and constraints

Templates should make important requirements unambiguous, including:

- The task objective and scope.
- Required inputs and assumptions.
- Constraints and prohibited actions.
- Expected output and deliverables.
- Acceptance criteria.
- Testing and verification requirements.
- Approval requirements for consequential changes.

### 3. Human oversight

Agents should ask questions when material requirements are unclear, identify assumptions, and request approval before performing unauthorized or destructive operations.

Templates should distinguish between actions an agent may execute independently and decisions that require human approval.

### 4. Durable project knowledge

Important decisions and requirements should be recorded in repository files rather than existing only in conversational context.

Prompts should encourage agents to update the relevant documentation, instructions, schemas, and decision records when approved changes affect them.

### 5. Independent verification

Agents should verify their work using tests, linters, type checkers, build tools, schemas, security checks, and other appropriate mechanisms.

An agent's assertion that a task is complete is not a substitute for evidence that the result works.

### 6. Security by default

Templates should encourage least privilege, safe defaults, explicit trust boundaries, secure secret handling, dependency hygiene, and appropriate review of generated code.

Instructions and skill files are not security boundaries by themselves; actual permissions and execution controls must be enforced by the surrounding environment.

### 7. Modular and maintainable resources

Each template should have a clear purpose, avoid unnecessary duplication, and be easy to discover and customize.

Prefer composable prompts, focused skills, and concise documentation over monolithic instructions that attempt to address every possible task.

## Using This Repository

1. **Identify the task.** Choose a prompt, skill, or template appropriate to the development activity.
2. **Review its assumptions.** Confirm that its intended language, framework, agent capabilities, and workflow match your project.
3. **Customize project-specific details.** Supply repository paths, architecture requirements, tool commands, security policies, and acceptance criteria.
4. **Provide the necessary context.** Give the agent access to the relevant source files, documentation, and tools.
5. **Review and approve changes.** Follow the template's approval requirements, especially when modifying existing repositories or performing consequential actions.
6. **Validate the result.** Run the appropriate checks and inspect the generated artifacts.
7. **Preserve useful knowledge.** Update project instructions and documentation so that subsequent agents can work consistently.

Do not assume a template is compatible with every harness simply because it uses plain text. Confirm which files and capabilities the selected agent actually recognizes.

## Template Authoring Guidelines

When adding a new prompt, skill, or reusable artifact:

- Use a descriptive, consistent filename.
- State its purpose and intended audience.
- Define required inputs and expected outputs.
- Identify prerequisites and supported tools.
- Separate mandatory requirements from recommendations.
- Include clear execution steps and acceptance criteria.
- Explain how errors, uncertainty, and missing information should be handled.
- Define when the agent must ask questions or obtain approval.
- Include validation steps where applicable.
- Avoid hard-coded credentials, machine-specific paths, and undocumented dependencies.
- Identify harness-specific assumptions.
- Include examples when they materially improve usability.
- Review existing resources before introducing overlapping functionality.

For skills, also document activation criteria and keep supporting scripts and reference material organized within the skill directory when the chosen format supports that structure.

## Quality and Maintenance

Resources should be maintained as reusable engineering assets rather than one-off prompts.

When practical:

- Validate structured metadata and configuration.
- Check links and referenced paths.
- Test scripts and examples.
- Verify compatibility with intended agent harnesses.
- Review templates when upstream specifications change.
- Remove obsolete or contradictory instructions.
- Record important compatibility limitations.
- Keep examples consistent with the documented conventions.

Do not label a template as tested or compatible unless the relevant verification has actually occurred.

## Contributing

Contributions are welcome, including new prompts, skill templates, developer workflows, documentation, and improvements to existing resources.

Before contributing:

1. Review existing resources to avoid unnecessary duplication.
2. Follow the established directory structure and naming conventions.
3. Keep changes focused and reusable.
4. Document assumptions, prerequisites, and limitations.
5. Validate links, syntax, scripts, and examples where applicable.
6. Explain how the contribution improves agent reliability, portability, or development efficiency.

See [`docs/contribution-guide.md`](docs/contribution-guide.md) for the contribution process, if present.

## Intended Audience

This repository is intended for:

- Software developers using AI coding assistants.
- Engineers building reusable agent skills and workflows.
- Teams standardizing AI-assisted development practices.
- Platform and developer-experience engineers.
- Security engineers establishing guardrails for agent-generated changes.
- Engineers building autonomous or multi-agent development systems.

## License

The repository's license should be defined in the root `LICENSE` file. Until a license is selected and added, do not assume that all contents are available for unrestricted redistribution or reuse.

---

**Objective:** Make AI-assisted software development more consistent, portable, secure, and verifiable through reusable prompts, skills, and developer templates.
