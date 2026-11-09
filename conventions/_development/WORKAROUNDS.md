# WORKAROUNDS

Maintain an inventory of active technical workarounds, hacks, and patches in `wiki/development/workarounds/`.

## Organization

- Group entries by affected project area. Reuse an existing scope where appropriate; keep entries inside their scope directory.
- Maintain a root index listing scope directories and a scope index listing all active entries in that scope.
- Name entries `YYYY_MM_DD_TYPE_SHORT_TOPIC.md` using the actual date added and `PATCH` or `WORKAROUND` as the type.

## Entries

- Create an entry and add it to the scope index when introducing a workaround. Update the existing entry when changing it; do not create duplicates. Add new scopes to the root index.
- Record the problem and reason, affected components and versions, links to the implementation or patch, verification performed, and removal conditions. Include known upstream issues or pull requests, distinguishing the same defect from a merely similar one.

## Dependency updates

- Before updating dependencies, read the relevant scope indexes and entries and check upstream fixes.
- After updating, verify each affected workaround and its original failure scenario. Keep, adapt, or remove it as appropriate. A version change or a patch failing to apply does not by itself prove the underlying issue is fixed.
- Record dated review results in retained or adapted entries.

## Removal

- When a workaround is removed and its original failure scenario has been verified, remove its entry and scope-index link in the same change. Keep the inventory limited to active workarounds.
- Record significant verification in the done journal when its entry criteria apply.
