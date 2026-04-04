---
description: Full config reference for EzDonutDiscord with defaults and placeholders.
---

# Configuration

After first startup, EzDonutDiscord creates `/plugins/EzDonutDiscord/config.yml`.

## Default `config.yml`

```yaml
# EzDonutDiscord v1.0.0 - config.yml
link:
  raw: "https://discord.gg/donutsmp"
  display: "discord.gg/donutsmp"

message:
  discord:
    enabled: true
    lines:
      - "&#00A4FCJoin the DonutSMP Discord community!"
      - "&#00A4FC&l*&r &f&n%link_display%"
    hover:
      - "&#00A4FCOpen the Discord invite"
  actionbar:
    enabled: true
    text: "&7The link has been sent in chat!"
  reload:
    enabled: true
    lines:
      - "&#00A4FC&l*&r &f&nReloaded the config!"

sounds:
  pling:
    enabled: true
    sound: "BLOCK_NOTE_BLOCK_PLING"
    volume: 0.5
    pitch: 1.0

placeholderapi:
  enabled: true
```

## Key Reference

### `link`

```yaml
raw: "https://discord.gg/donutsmp" # Type: String | URL opened when the invite is clicked
display: "discord.gg/donutsmp" # Type: String | Visible invite text shown in chat
```

### `message`

```yaml
discord:
  enabled: true # Type: Boolean | Enables /discord chat output
  lines: # Type: List<String> | %link_display% and %link_raw% are replaced before sending
    - "&#00A4FCJoin the DonutSMP Discord community!"
    - "&#00A4FC&l*&r &f&n%link_display%"
  hover: # Type: List<String> | Hover text for clickable invite lines
    - "&#00A4FCOpen the Discord invite"
actionbar:
  enabled: true # Type: Boolean | Enables action bar response for players
  text: "&7The link has been sent in chat!" # Type: String | Action bar text after /discord
reload:
  enabled: true # Type: Boolean | Enables custom /discord reload response
  lines: # Type: List<String> | Reload confirmation lines
    - "&#00A4FC&l*&r &f&nReloaded the config!"
```

### `sounds`

```yaml
pling:
  enabled: true # Type: Boolean | Plays a sound after /discord and /discord reload
  sound: "BLOCK_NOTE_BLOCK_PLING" # Type: String | Bukkit enum or namespaced sound key
  volume: 0.5 # Type: Double | Playback volume
  pitch: 1.0 # Type: Double | Playback pitch
```

### `placeholderapi`

```yaml
enabled: true # Type: Boolean | Enables PlaceholderAPI parsing/expansion when installed
```

## Built-In Message Placeholders

- `%link_raw%` → full URL from `link.raw`
- `%link_display%` → visible invite text from `link.display`

> Tip: PlaceholderAPI placeholders are also parsed when PlaceholderAPI is installed, `placeholderapi.enabled: true`, and the sender is a player.

## Formatting Notes

- Standard Bukkit formatting (`&7`, `&c`, `&l`) is supported.
- Hex color format (`&#00A4FC`) is supported.
- Click events only apply on lines containing `%link_display%`.
