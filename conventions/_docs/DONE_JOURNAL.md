# DONE JOURNAL

Store completed work in `wiki/done/` and keep its index current. The journal records results; the task tracker owns current status.

## When to create an entry

- **A commit changes code:** include one short entry in that same commit. Use `YYYY_MM_DD_TYPE_SHORT_TOPIC.md`, with a type such as `FIX`, `REF`, or `FEAT`. A documentation-only commit does not qualify on this basis.
- **The user explicitly accepts a tracked task:** create one `YYYY_MM_DD_TASK_<TASK_ID>.md` entry. Use uppercase letters, digits, and underscores for the ID in the filename. In the entry, retain the original ID and task link, report the outcome and checks, and link any existing code-commit entries.
- **A significant configuration or integration check finishes:** use the actual check date in `YYYY_MM_DD_CHECK_SHORT_TOPIC.md`. Record the environment and versions, static and runtime checks, outcome, and limitations. If the check belongs to the current commit's entry, extend that entry instead. Verification does not establish user acceptance.

Report routine test runs and review iterations in the response or task. A journal entry does not authorize a commit, push, or task closure.

## Format

Use sections for context, changes, and limitations. State what was requested or wrong, how the cause or result was established, and what changed. Bold key results or limits, not whole paragraphs. Link to the entry instead of creating separate `VERIFICATION*.md` reports among active instructions.

## Immutable history

- Do not modify journal entries that do not belong to the current commit. This includes local-file links: preserve them even when their targets no longer exist.
- Record new results or corrections in a separate entry only when one of the entry criteria applies.
