---
description: Command reference for EzDonutDiscord.
---

# Commands

This page lists the supported commands and required permissions.

## Command Reference

| Command | Description | Permission |
|---|---|---|
| `/discord` | Sends the configured Discord invite and, for players, can also show action bar + pling sound. | `ezdonutdiscord.discord` |
| `/discord reload` | Reloads `config.yml` and refreshes PlaceholderAPI integration state. | `ezdonutdiscord.reload` |

## Notes

- `reload` tab completion only appears to senders who already have reload access.
- Use `/discord reload` for config/message changes; prefer full restarts for plugin updates.
