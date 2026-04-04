---
description: PlaceholderAPI integration behavior and placeholder list.
---

# PlaceholderAPI

PlaceholderAPI support is optional. EzDonutDiscord detects PlaceholderAPI at runtime and can both parse placeholders inside its messages and register EzDonutDiscord-specific placeholders.

## Built-In EzDonutDiscord Placeholders

When PlaceholderAPI is installed and enabled, EzDonutDiscord registers:

- `%ezdonutdiscord_link_raw%`
- `%ezdonutdiscord_link_display%`

Values are read from `link.raw` and `link.display` in `config.yml`.

## Parsing Inside Plugin Messages

EzDonutDiscord can parse PlaceholderAPI placeholders inside:

- `message.discord.lines`
- `message.discord.hover`
- `message.actionbar.text`
- `message.reload.lines`

Parsing occurs only when all conditions are true:

- PlaceholderAPI is installed
- `placeholderapi.enabled` is `true`
- sender is a player

## Reload Behavior

Running `/discord reload` refreshes PlaceholderAPI integration. If PlaceholderAPI was added, removed, or disabled, EzDonutDiscord updates expansion registration during reload.
