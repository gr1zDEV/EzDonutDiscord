---
description: End-to-end behavior of the /discord command output.
---

# Discord Message Flow

EzDonutDiscord centers around one player-facing command, but the output is assembled from multiple config sections: clickable chat component, optional hover text, optional action bar, and optional sound.

## What Happens on `/discord`

1. Plugin checks `ezdonutdiscord.discord` or `ezdonutdiscord.admin`.
2. If `message.discord.enabled` is `false`, sender receives the disabled notice.
3. Each line in `message.discord.lines` is processed and sent in order.
4. If a line contains `%link_display%`, that portion becomes clickable and opens `link.raw`.
5. If `message.discord.hover` has text, hover text is attached to the clickable component.
6. If sender is a player, action bar and pling sound may be sent based on config.

## Practical Notes

- Only `%link_display%` segments are clickable.
- `/discord reload` can also reuse the same pling sound profile for players.
- `ezdonutdiscord:discord` is hidden from normal player command lists unless they have reload-level access.
