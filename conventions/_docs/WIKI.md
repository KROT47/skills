# WIKI

## Reading and editing

- Use the `wiki/` files in the current checkout or worktree.
- Use the repository's documented search tool if it has one; otherwise search the Markdown files directly.
- Respect access limits and read the matching pages and their declared sections.
- Use native file tools for changes; a running wiki service is unnecessary.

- Follow the repository's page format when changing metadata, sections, or attachments.
- Where the format supports icons, give each new page a relevant emoji and preserve existing icons unless a change was requested.

## Moves and deletions

- When moving a page, preserve its ID and its associations with sections and attachments. Give a copy a new ID. Before replacing or deleting content, confirm it can be recovered from version control or ordinary trash; otherwise keep it and report the blocker.
- Update affected indexes and editable incoming and outgoing [links](./LINKS.md). Leave [immutable journal entries](./DONE_JOURNAL.md#immutable-history) as they were.

## Agent entry points

A wiki entry point for agents should lead to the target checkout's root `AGENTS.md`. Its presence does not prove it was read. Maintain repository instructions, local skills, their manifests, and agent profiles with native file tools; keep role workflows at their owners.
