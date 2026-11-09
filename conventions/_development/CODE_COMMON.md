# CODE COMMON

Apply these rules when writing, refactoring, or reviewing code, including standalone CLI scripts.

## Readability

- Write simple code that is easy to read, change, and test.
- Preserve existing behavior during a refactor unless the task requires a change.
- Use concise, clear names consistent with the surrounding code and domain. Keep behavior-defining details in the name. Use the same term for the same concept.
- Give each function one clear responsibility.
- Extract a function when its name makes a process easier to understand or removes repeated logic.
- Do not extract trivial code if the new function only adds another step for the reader.
- Keep each main process easy to follow. Show its steps in execution order.
- Separate logical blocks with blank lines. Keep related statements together.
- Remove duplicate logic when the code has the same purpose and the same rules. Do not combine code only because it looks similar.
- Use comments to explain reasons, constraints, and decisions that the code does not make clear. Do not repeat what the code already says.
- Before changing behavior, find the code that already owns it; make the change there and reuse existing implementations.
- Keep important business rules in their existing domain operation, including its checks.
- Prefer existing project tools and standard library features before adding dependencies.
- Do not add abstractions or configuration options for possible future needs.

## Verification

- Update affected commands, configuration, tests, and documentation after moving files.
- Run the relevant tests, static checks, lint checks, and builds available in the project.
- Test affected entry points in their actual runtime.
- Preserve unrelated changes and existing staged content.
- Report what changed, which checks passed, and which checks you could not complete.
