# Agent Compatibility

This guide explains how to use the repository's prompts, skills, and templates with different AI coding agents and development environments.

## Compatibility Philosophy

The repository favors portable instructions over agent-specific syntax. Prompts should describe the task, constraints, workflow, and expected results without assuming a particular vendor, model, IDE, or command-line interface.

Portability does not mean every resource works identically in every agent. Tools differ in their ability to inspect files, edit a repository, execute commands, retain context, access the network, or load reusable skills.

## Resource Types and Portability

| Resource type | Typical portability | Compatibility considerations |
|---|---|---|
| Plain Markdown prompt | High | The agent must receive the prompt and relevant project context. |
| Markdown template | High | The user or agent must populate placeholders and save the result in the appropriate location. |
| Agent skill | Depends on format | Skill discovery, metadata, directory layout, and loading behavior may be tool-specific. |
| Tool configuration | Low to medium | Configuration keys, permissions, and execution behavior vary by agent. |
| Workflow or automation | Depends on implementation | Shell, runtime, credentials, permissions, and CI environment may differ. |

Use plain Markdown for core instructions whenever possible. Add tool-specific metadata only when required by the target environment.

## General Usage

For an agent that accepts a prompt directly:

1. Open the relevant `prompts/<category>/prompt.md` file.
2. Provide the prompt to the agent.
3. Replace task-specific placeholders or supply the missing context.
4. Identify the repository and the intended scope of work.
5. Review the proposed plan and changes.
6. Confirm that the agent's verification report matches the checks actually performed.

For an agent that can read repository files, ask it to inspect the prompt file and follow its instructions. Do not assume that the agent has access to the local filesystem simply because it is conversational.

## Repository Instructions

Many coding agents support repository-level instruction files, but their filenames, formats, discovery rules, and precedence differ.

Before integrating a resource into an agent-specific instruction file:

- Check the agent's current documentation.
- Confirm where the agent expects project instructions and skill definitions.
- Verify whether instructions are loaded automatically or must be explicitly selected.
- Check context-length limits and any instruction-priority rules.
- Avoid copying large prompts into global instructions when they are only relevant to a particular task.
- Keep project-specific constraints separate from general-purpose reusable prompts where practical.

Do not assume that a filename recognized by one tool will be recognized by another.

## Skills and Agent-Specific Formats

Skills may require metadata, a prescribed directory layout, or a specific entrypoint. The content of a skill may be portable even when its packaging is not.

When creating or adapting a skill:

1. Identify the target agent and the supported skill format.
2. Consult the current official specification or documentation.
3. Preserve the skill's purpose and behavioral requirements.
4. Adapt only the metadata, packaging, and integration details required by the target.
5. Keep references and examples within the skill's directory when required by the format.
6. Test that the agent discovers and uses the skill as expected.
7. Document any capabilities or tools the skill assumes.

For ecosystems that support the Agent Skills specification, consult the current specification at <https://agentskills.io/> and verify the target tool's implementation details. Support for a specification may vary by agent and version.

## Tool Access and Permissions

A prompt can request an action that the selected agent cannot perform. Examples include executing tests, accessing a remote service, reading a protected file, or modifying a repository.

Before a workflow begins, establish which capabilities are available:

- File and repository access.
- Shell or command execution.
- Network access.
- Installed language runtimes and dependencies.
- Access to test services and fixtures.
- Permissions to modify files or invoke external systems.

Agents must not claim to have performed an action when the necessary tool was unavailable. If execution is not possible, they should provide the relevant commands and clearly mark verification as not performed.

Grant only the permissions necessary for the task. Review commands that modify state, delete data, change infrastructure, or access production resources before execution.

## Shell and Platform Differences

Commands may vary across macOS, Linux, and Windows, as well as across shells and package managers.

When portability matters:

- Prefer commands already used by the repository.
- Inspect project scripts and CI workflows for authoritative commands.
- State the required shell and platform when a command is platform-specific.
- Avoid assuming GNU-specific utilities are available on macOS.
- Avoid assuming a package manager or runtime is installed.
- Provide platform alternatives only when they are needed and can be maintained.
- Never invent successful command output.

If a prompt requires a command that may be destructive, explain its effects and require appropriate authorization.

## Model and Context Differences

Different models may vary in reasoning, context capacity, tool use, and instruction adherence. Keep critical requirements explicit and near the relevant task instructions.

For more reliable results:

- Supply the actual task and relevant source context.
- Break large tasks into reviewable steps.
- Ask for assumptions and unresolved questions to be surfaced.
- Require evidence for important conclusions.
- Validate output independently rather than relying on confidence or verbosity.
- Avoid depending on undocumented model-specific behavior.

## Compatibility Testing

When a resource is intended for a specific agent or a defined set of agents, document:

- Agent and version tested, if known.
- Model or runtime constraints that materially affect usage.
- Required tools and permissions.
- Installation or discovery procedure.
- Test task or validation method.
- Known incompatibilities and limitations.

Use explicit status labels such as:

- **Designed for:** Intended target, not necessarily tested.
- **Tested:** Executed in the stated environment with the observed result.
- **Partially tested:** Some capabilities or scenarios remain unverified.
- **Untested:** No execution-based compatibility validation has been performed.

Do not describe a resource as universally compatible based solely on its use of Markdown.

## Troubleshooting

### The agent ignores the prompt

Confirm that the prompt was actually provided, relevant repository instructions were loaded, and conflicting instructions are not present. Reduce ambiguity and make the critical constraints explicit.

### The agent cannot find a skill

Check the target agent's supported skill location, metadata requirements, naming rules, and discovery behavior. Confirm whether a restart or explicit skill selection is required.

### The agent cannot run tests

Check available tools, runtime versions, dependencies, permissions, and environment configuration. Have the agent report the exact limitation rather than claim success.

### The agent makes unrelated changes

Narrow the scope, request a plan before editing, and require a final diff review. Split broad tasks into smaller changes when appropriate.

### A command works on one platform but not another

Confirm the shell, utility implementations, path conventions, and runtime versions. Document the supported environment or provide tested alternatives.

## Updating Compatibility Guidance

Agent capabilities and configuration formats change. When updating agent-specific instructions:

1. Consult current official documentation.
2. Record the target version or date of validation where useful.
3. Test discovery, execution, and expected output.
4. Update related examples and links.
5. Preserve the portable core of the resource where possible.
