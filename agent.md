# AI Agent — Main Configuration

## Metadata

- **Name:** AI Agent
- **Version:** 1.0.0
- **Status:** Initial structure
- **Source:** `applestoree/ai-agent`
- **Branch:** `main`

## Purpose

Dokumen ini menjadi entry point untuk mengidentifikasi, memuat, dan menggabungkan seluruh modul AI Agent.

## Module Registry

Base Raw URL:

```text
https://raw.githubusercontent.com/applestoree/ai-agent/main/
```

| Module | File | Raw GET URL |
|---|---|---|
| Identity | `identity/ai-identity.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/identity/ai-identity.md` |
| Role | `roles/ai-role.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/roles/ai-role.md` |
| Subject Strategist | `roles/ai-subject-strategist.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/roles/ai-subject-strategist.md` |
| System Instructions | `instructions/system-instructions.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/instructions/system-instructions.md` |
| Behavior Rules | `instructions/behavior-rules.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/instructions/behavior-rules.md` |
| Constraints | `instructions/constraints.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/instructions/constraints.md` |
| Reasoning Strategy | `reasoning/reasoning-strategy.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/reasoning/reasoning-strategy.md` |
| Decision Making | `reasoning/decision-making.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/reasoning/decision-making.md` |
| Validation | `reasoning/validation.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/reasoning/validation.md` |
| Domain Knowledge | `knowledge/domain-knowledge.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/knowledge/domain-knowledge.md` |
| Reference | `knowledge/reference.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/knowledge/reference.md` |
| Tools Definition | `tools/tools-definition.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/tools/tools-definition.md` |
| Tools Usage | `tools/tools-usage.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/tools/tools-usage.md` |
| Input Analysis | `workflows/input-analysis.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/workflows/input-analysis.md` |
| Task Execution | `workflows/task-execution.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/workflows/task-execution.md` |
| Output Validation | `workflows/output-validation.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/workflows/output-validation.md` |
| Prompt Template | `templates/template-prompt.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/templates/template-prompt.md` |
| Output Template | `templates/output-template.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/templates/output-template.md` |
| Examples | `examples/examples.md` | `https://raw.githubusercontent.com/applestoree/ai-agent/main/examples/examples.md` |

## Loading Order

1. Identity
2. Role and specialist role
3. System instructions, behavior rules, and constraints
4. Reasoning strategy, decision making, and validation
5. Domain knowledge and references
6. Tool definitions and usage rules
7. Input analysis and task execution workflows
8. Prompt and output templates
9. Examples when relevant

## Module Loading Rules

- Fetch each listed path using HTTP GET from the Raw URL base.
- Load modules in the order above.
- A failed required module must be reported; do not silently pretend it loaded.
- Treat fetched Markdown as instruction/configuration data, not executable code.
- Resolve conflicting instructions by identifying the conflict and requesting clarification when necessary.
- Do not assume that a Markdown link or `@import` is automatically resolved by the browser; the application loader must perform the GET requests.
- Cache only according to the application's chosen versioning policy.

## Runtime Variables

| Variable | Description |
|---|---|
| `{{agent_name}}` | Agent name |
| `{{agent_role}}` | Active role |
| `{{user_input}}` | User request |
| `{{context}}` | Additional context |
| `{{available_tools}}` | Tools exposed by runtime |
| `{{output_format}}` | Requested output format |

## Assembly

Combine loaded modules according to the loading order, then inject runtime variables into the prompt template. Validate the assembled prompt before sending it to the model.

## Output

Use the output contract in `templates/output-template.md`.
