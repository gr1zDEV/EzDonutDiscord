---
description: Common questions for setup, behavior, and debugging.
---

# FAQ

## The plugin is not loading. What should I check first?
Confirm your server is running Java 21+ and Paper/Folia 1.21+, then inspect `logs/latest.log` for startup errors.

## Can I use this on Folia?
Yes. EzDonutDiscord is marked as Folia-supported.

## Why are PlaceholderAPI placeholders not resolving?
Confirm PlaceholderAPI is installed, `placeholderapi.enabled` is `true`, and you are testing as a player. Console senders do not get PlaceholderAPI parsing.

## Why can some staff tab-complete `/discord reload` but others cannot?
Only senders with `ezdonutdiscord.reload` or `ezdonutdiscord.admin` can see and use reload completion.

## Can I reload config without restarting the whole server?
Yes. Use `/discord reload`. For jar updates, full restart is still recommended.

## Is there a full checklist for common issues?
Yes. See [Troubleshooting](usage/troubleshooting.md) for symptom-based fixes.
