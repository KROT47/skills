# SHARED LOGGER

Apply these rules when adding or changing logging within a service or application.

## Shared logger

- Use one shared logger within the current service or application.
- Reuse the existing logger. Do not create a second logging system.
- If no logger exists, create a minimal logger in a separate file. Follow the conventions of the language and the project.
- Use standard logging facilities when available. Do not build a custom logging framework.
- Import the shared logger into the files that need logging.
- Keep log formatting and output configuration in the shared logger.

## Log levels

- Use the logger's standard methods and supported levels.
- Use `debug` for details that help diagnose a problem, such as a relevant state change or a branch decision.
- Use `info` for important events in normal operation, such as service readiness or completion of a significant operation.
- Use `warning` or `warn` for unexpected conditions that permit continued operation, such as a fallback or a recoverable failure.
- Use `error` when an operation fails or the system cannot complete the requested action.
- Use other levels only when the project defines their purpose.
- Do not report a failure as a successful operation.

## What to log

- Log important process stages, significant state changes, and failures.
- Log the start of a long or important operation when this helps identify where execution stopped.
- Log completion only after the result is known.
- Do not log every function call, loop iteration, or variable assignment.
- Avoid repeated messages that add no useful information.
- Keep routine diagnostic details at `debug` level.

## Messages and context

- State what happened. Name the operation or component.
- Use clear, consistent messages for the same event.
- Include the variable values and states needed to understand the event.
- Include relevant identifiers so related messages can be traced across a process.
- For a state change, include the previous and new states when useful.
- For a retry, include the attempt number and the reason.
- For a failure, include useful error details and the stack trace when available.
- Use structured fields when the logger supports them. Do not assemble all context into a long message.
- Do not dump complete objects or payloads when a few fields are sufficient.

## Safety and reliability

- Do not log passwords, access tokens, private keys, or other secrets.
- Exclude unnecessary personal data. Mask sensitive values when they are required for diagnosis.
- Limit the size of logged values. Do not log unbounded payloads.
- Avoid logging the same error at every layer. Log it where the code handles it or reports the final failure.
- Do not add expensive calculations only to produce a disabled `debug` message.
- Keep diagnostic logs separate from machine-readable program output.
- Preserve application behavior when adding logs. Do not suppress errors or change control flow to make logging easier.

## Verification

- Check normal operation, failure handling, and relevant state transitions.
- Confirm that each message uses the correct level and includes useful context.
- Confirm that logs contain no secrets or unnecessary data.
- Check for duplicate messages and excessive output.
