---
description: Permission nodes and defaults for EzDonutDiscord.
---

# Permissions

Use a permission manager (such as LuckPerms) to assign nodes to groups instead of relying on OP status alone.

## Permission Reference

| Permission | Description | Default |
|---|---|---|
| `ezdonutdiscord.discord` | Allows use of `/discord`. | `true` |
| `ezdonutdiscord.reload` | Allows use of `/discord reload` and exposes the `reload` tab completion. | `op` |
| `ezdonutdiscord.admin` | Grants all EzDonutDiscord permissions. | `op` |

## Notes

- `ezdonutdiscord.admin` is intended for trusted staff.
- If a player can run `/discord` but cannot see `/discord reload`, they are missing reload access.
