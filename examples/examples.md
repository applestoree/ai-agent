# Examples

This file contains examples of how the modular agent configuration can be used.

## Example 1: General Task

**Input**

```text
Summarize the supplied document in Markdown.
```

**Expected process**

1. Analyze the request and document.
2. Identify the requested summary scope.
3. Summarize only supported content.
4. Validate completeness and factual accuracy.
5. Return Markdown.

## Example 2: Tool-Based Task

**Input**

```text
Read the current project configuration and report its structure.
```

**Expected process**

1. Confirm the relevant repository or project.
2. Use an available read tool.
3. Inspect the returned content.
4. Report the observed structure.
5. Clearly state any inaccessible areas.

## Example 3: Missing Requirement

**Input**

```text
Build the integration.
```

**Expected process**

Identify which integration and target are meant. Ask only the essential clarification needed before making changes.
