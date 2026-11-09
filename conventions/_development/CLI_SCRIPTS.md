# CLI SCRIPTS

## Scope

This document applies **only to standalone CLI scripts**, including shell, TypeScript, and Python utilities. The layout rules also apply to helper modules and tests for these CLI utilities.

**TypeScript/JavaScript application code, configuration, build tooling, bundler plugins, and application tests with their helpers are outside this document's scope.** A `scripts` entry in `package.json` or execution through Node/Yarn does not make that code a CLI script under these rules. Follow the conventions of the relevant application for its structure.

## Files and execution

- Within each independent scope of CLI utilities, place user commands in `scripts/`, modules used by those commands in `scripts/utils/`, and CLI utility tests in `scripts/tests/`. Name the test directory `tests/` and place it beside `utils/`, not inside it. In repository workflows, keep groups organized by purpose, each with its own `utils/` and `tests/`. Do not nest `scripts/` inside another `scripts/`.
- Separate CLI utility files by purpose, not just by name: place test runners, offline/live/smoke tests, and helpers/fixtures used only by tests in `tests/`; keep runtime validation and other operational utilities in `utils/`. Do not move dependency, vendor, or generated files to satisfy this convention.
- Place CLI utilities for third-party services in `services/<service>/scripts/`. Do not add a root CLI launcher without a need.
- Keep standalone status/logs/stop/backup/restore operations as user commands. When moving files, preserve working directory, configuration, and data semantics. Do not move unrelated scopes in bulk without a request.
- Use `snake_case` names and the extension appropriate to the language. Preserve the agreed names of existing public service commands. New Python utilities, including those invoked by agents, must be executable `.py` files, use Python 3.11+, and have a shebang on the first line and a short header. Keep shell for simple operations; do not create wrappers just to provide a `.sh` file.
- Resolve paths inside a script independently of the working directory. Show commands with an explicit working directory: `./scripts/…` from the repository root, or `cd services/<service>` followed by a service-local command.

## Simplicity and responsibility

- Keep scripts minimal and perform the work in as few steps as necessary.
- Extract separate utility scripts only for independent operations with clear responsibilities, inputs, and results. Group related operations in subdirectories by purpose.
- A separate command is justified when it is useful to run, test, review, and maintain independently. Do not create a script for every algorithm step or small function.
- Keep helper functions inside the script or a shared importable module. Do not turn them into separate executable commands or add wrappers without an independent responsibility.
- Prefer shell for simple CLI scripts. When a task requires functionality or complexity that shell does not handle well, prefer TypeScript. Apply the same rule to CLI commands called directly by agents; do not rewrite existing working scripts solely to change their language.
- The goal is to separate meaningful operations and simplify maintenance.

## Confirmation and input

- **One explicit confirmation is enough for the entire scope shown for the current run, including helpers.** Before making changes, briefly show the target and actions, including access, downloads, and persistent settings. After consent, do not ask again at every step; a refusal ends the run without changes.
- Do not silently expand the confirmed scope. If a conflict arises or a different action is needed, stop and explain the next step.
- Validate required input before dependent requests and changes, and non-secret parameters before requesting keys. Show the default in the prompt; Enter selects it. Retry invalid interactive input in place; an invalid CLI argument ends the command with guidance.
- Reuse existing settings and completed steps on subsequent runs; do not overwrite data or keys or create duplicates. Do not expose secrets in logs, argv, or documentation.

## Output and documentation

- By default, show only the required input, significant result, and next action. Omit successful internal checks and repeated summaries; provide details through `--check`/`--verbose`.
- Errors must explain the cause and how to continue. Do not proceed with dependent steps or print the full inventory after a single blocker.
- Keep the README to brief prerequisites, a command, and the next step. Explain mechanics in the header/`--help`, and link to canonical documentation for processes.
