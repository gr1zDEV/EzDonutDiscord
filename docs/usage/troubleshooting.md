---
description: Symptom-based fixes for common EzDonutDiscord issues.
---

# Troubleshooting

Use this page when `/discord` or `/discord reload` does not behave as expected.

## Quick Checklist

1. Server is running Java 21+ and Paper/Folia 1.21+.
2. Plugin jar is in `/plugins/` and server was fully restarted.
3. `/plugins/EzDonutDiscord/config.yml` exists and is valid YAML.
4. Sender has the correct permission node.
5. You ran `/discord reload` after config edits.

## Symptom Guide

| Symptom | Most Likely Cause | Fix |
|---|---|---|
| Nothing happens with `/discord` | Missing `ezdonutdiscord.discord` | Grant `ezdonutdiscord.discord` (or `ezdonutdiscord.admin`) via LuckPerms. |
| `/discord reload` is unknown or denied | Missing `ezdonutdiscord.reload` | Grant `ezdonutdiscord.reload` to trusted staff. |
| Invite text appears but is not clickable | `%link_display%` missing from message line | Add `%link_display%` to one of `message.discord.lines`. |
| Click opens wrong URL | `link.raw` misconfigured | Set `link.raw` to the full invite URL, including `https://`. |
| Hover text does not show | `message.discord.hover` empty | Add at least one line under `message.discord.hover`. |
| Action bar does not appear | `message.actionbar.enabled` is `false` or sender is console | Enable action bar; console cannot receive it. |
| Sound does not play | Sound disabled or invalid key | Set `sounds.pling.enabled: true` and verify `sounds.pling.sound`. |
| PlaceholderAPI values stay raw | PlaceholderAPI missing/disabled, or sender is console | Install PlaceholderAPI, keep `placeholderapi.enabled: true`, and test as a player. |

## PlaceholderAPI Debug

- Confirm PlaceholderAPI is installed and loaded on startup.
- Run `/papi parse me %ezdonutdiscord_link_raw%` to verify expansion output.
- If PlaceholderAPI was installed after boot, run `/discord reload` or restart.

## Safe Operations

- Prefer full restarts for plugin updates.
- Use `/discord reload` for config/message edits.
- Avoid Bukkit `/reload`.
