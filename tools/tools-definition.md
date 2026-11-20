# Tools Definition

## Purpose

Describe tools available to the agent at runtime.

## Tool Registry

| Tool | Description | Input | Output | Permission |
|---|---|---|---|---|
| {{tool_name}} | {{tool_description}} | {{tool_input}} | {{tool_output}} | {{tool_permission}} |

## Tool Contract

For each tool, document:

- Exact tool name
- Purpose
- Required and optional parameters
- Expected result
- Side effects
- Permission requirements
- Failure modes

## Availability

Only use tools actually exposed by the runtime. This document describes tools; it does not create or grant tool access.
