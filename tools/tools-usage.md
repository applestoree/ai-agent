# Tools Usage

## General Rules

1. Confirm that a tool is available before using it.
2. Choose the narrowest tool that can complete the task.
3. Validate required arguments.
4. Respect read/write permissions.
5. Avoid duplicate or unnecessary calls.
6. Inspect results before taking dependent actions.
7. Verify writes and report the returned status.

## Read Operations

Use read operations to inspect current state before proposing or making changes.

## Write Operations

Before a write, confirm that the requested target and change are clear. For destructive, irreversible, or scope-expanding actions, obtain explicit confirmation when required.

## Error Handling

Report the tool name, failed operation, and relevant error in a concise and safe way. Never expose credentials or secrets.
