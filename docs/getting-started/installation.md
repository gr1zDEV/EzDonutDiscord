---
description: Install, update, and remove EzDonutDiscord safely.
---

# Installation

Use this guide to install EzDonutDiscord on Paper or Folia, update it cleanly, and remove it without leaving stale files.

## Requirements

| Item | Required Version |
|---|---|
| Java | 21+ |
| Server Software | Paper or Folia 1.21+ |
| Required Plugins | None |
| Optional Plugins | PlaceholderAPI 2.11.6+ |

## Install Steps

1. Download the latest plugin jar, or build from source with `mvn package`.
2. Put `EzDonutDiscord-1.0.0.jar` in your `/plugins/` folder.
3. Start the server with a full restart to generate `/plugins/EzDonutDiscord/config.yml`.
4. Update your Discord invite values in the config.
5. Run `/discord` in-game to verify chat output, action bar, and sound.

> Warning: Do a full restart when installing or updating. Avoid Bukkit `/reload`.

## Update Steps

1. Stop your server.
2. Replace the existing jar with the new jar.
3. Start the server.
4. Review [Configuration](configuration.md) for any new keys.

> Tip: `/discord reload` is best for message/config edits, not binary upgrades.

## Uninstall Steps

1. Stop your server.
2. Remove the plugin jar from `/plugins/`.
3. Optionally delete `/plugins/EzDonutDiscord/` to remove config data.
