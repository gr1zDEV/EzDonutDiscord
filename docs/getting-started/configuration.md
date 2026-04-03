# Configuration

After first run, EzDonutDiscord creates its config at `/plugins/EzDonutDiscord/config.yml`.

## config.yml

```yaml
# EzDonutDiscord v1.0.0 - config.yml
link: # Discord invite values used by the command and placeholders
  raw: "https://discord.gg/donutsmp" # Full URL opened when players click the invite
  display: "discord.gg/donutsmp" # Text shown in chat for the clickable invite

message: # All chat, action bar, and reload message settings
  discord: # Chat output sent by /discord
    enabled: true # Enables or disables the main Discord chat message
    lines: # Each entry is sent as one chat line
      - "&#00A4FCJoin the DonutSMP Discord community!" # Header line shown before the clickable invite
      - "&#00A4FC&l*&r &f&n%link_display%" # Clickable invite line; %link_display% becomes the visible link text
    hover: # Hover text applied to the clickable invite component
      - "&#00A4FCOpen the Discord invite" # Hover line shown when players mouse over the invite
  actionbar: # Action bar confirmation shown to players after /discord
    enabled: true # Enables or disables the action bar response
    text: "&7The link has been sent in chat!" # Action bar text shown after the command runs
  reload: # Response sent after /discord reload
    enabled: true # Enables or disables the custom reload message
    lines: # Each entry is sent as one reload confirmation line
      - "&#00A4FC&l*&r &f&nReloaded the config!" # Reload confirmation text

sounds: # Optional sound feedback settings
  pling: # Single sound profile used by /discord and /discord reload
    enabled: true # Enables or disables the notification sound
    sound: "BLOCK_NOTE_BLOCK_PLING" # Bukkit sound name or namespaced Minecraft sound key
    volume: 0.5 # Playback volume for the configured sound
    pitch: 1.0 # Playback pitch for the configured sound

placeholderapi: # PlaceholderAPI integration settings
  enabled: true # Enables PlaceholderAPI parsing and expansion registration when PlaceholderAPI is installed
```

## Options Reference

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `link.raw` | String | `https://discord.gg/donutsmp` | Full URL opened when the clickable invite is pressed. |
| `link.display` | String | `discord.gg/donutsmp` | Text shown in chat for the invite component. |
| `message.discord.enabled` | Boolean | `true` | Enables the main `/discord` chat output. |
| `message.discord.lines` | List<String> | `2 lines` | Chat lines sent by `/discord`; `%link_display%` and `%link_raw%` are replaced before sending. |
| `message.discord.hover` | List<String> | `1 line` | Hover text attached to the clickable invite when a `%link_display%` line is present. |
| `message.actionbar.enabled` | Boolean | `true` | Enables the action bar confirmation for players. |
| `message.actionbar.text` | String | `&7The link has been sent in chat!` | Text shown in the action bar after `/discord`. |
| `message.reload.enabled` | Boolean | `true` | Enables the custom response after `/discord reload`. |
| `message.reload.lines` | List<String> | `1 line` | Reload confirmation message lines. |
| `sounds.pling.enabled` | Boolean | `true` | Plays the configured sound after `/discord` and `/discord reload`. |
| `sounds.pling.sound` | String | `BLOCK_NOTE_BLOCK_PLING` | Sound enum or namespaced key used for playback. |
| `sounds.pling.volume` | Double | `0.5` | Volume used for the pling sound. |
| `sounds.pling.pitch` | Double | `1.0` | Pitch used for the pling sound. |
| `placeholderapi.enabled` | Boolean | `true` | Enables PlaceholderAPI parsing and automatic expansion registration when PlaceholderAPI is installed. |

## Message Placeholders

- `%link_raw%` inserts the full invite URL from `link.raw`.
- `%link_display%` inserts the visible invite text from `link.display`.

> Tip: PlaceholderAPI placeholders are also parsed inside EzDonutDiscord messages when PlaceholderAPI is installed, `placeholderapi.enabled` is `true`, and the sender is a player.

## Formatting Notes

- Standard Bukkit color codes such as `&7`, `&c`, and `&l` are supported.
- Hex colors such as `&#00A4FC` are supported.
- The clickable invite only appears on message lines that include `%link_display%`.
