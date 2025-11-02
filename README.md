# KrakenLevels 2

Lightweight levels and missions plugin for modern Paper servers.

Originally created by Aglerr. This fork modernizes the codebase and configuration while staying simple to set up.

## Compatibility

- Minecraft server: 1.21.X only
- Platform: Paper or forks (e.g., Leaf)
- Tested on: LeafMC 1.21.X
- Backports: I do not plan to support older Minecraft versions

Requirements:
- Java 21 (required by Paper 1.21)

## Quick setup

1) Download the plugin jar and drop it into `plugins/`
2) Start the server once to generate config files
3) Configure the plugin (see next section)
4) Restart the server

## Configure

Main settings live in `plugins/KrakenLevels/config.yml`.

- Storage
  - MongoDB (recommended for networks/large servers)
  - YAML files (simple local storage)

Choose the storage:

```yaml
database:
  use-mongodb: true   # set to false to use YAML storage
```

MongoDB connection (if enabled):

```yaml
mongodb:
  host: localhost
  port: 27017
  database: krakenlevels
  username: ""
  password: ""
```

Other files to adjust:
- `levels.yml` – minimal example levels (one example per action)
- `messages.yml` – all user-facing messages
- `materials.yml` – material/entity display names

## Commands (basic)

- `/levels` – open the levels GUI
- `/mission` – mission menu and admin tools (see in-game help)

Permissions are standard and follow the `krakenlevels.*` pattern.

## Placeholders

This plugin registers PlaceholderAPI placeholders under the `krakenlevels` identifier.

| Placeholder | Description |
|---|---|
| `%krakenlevels_level%` | Player's current level |
| `%krakenlevels_nextlevel%` | Next level number (capped at max) |
| `%krakenlevels_getmaxlevel%` | Maximum level defined in levels.yml |
| `%krakenlevels_cost%` | Cost for the current level |
| `%krakenlevels_nextcost%` | Cost for the next level |
| `%krakenlevels_cost_formatted%` | Current level cost (formatted) |
| `%krakenlevels_nextcost_formatted%` | Next level cost (formatted) |
| `%krakenlevels_tasktype%` | Next level task type (Economy/Break blocks/Place blocks/Kill mobs/Fish) |
| `%krakenlevels_progress%` | Progress toward next level (current/required) |
| `%krakenlevels_currentprogress%` | Current progress value for next level |
| `%krakenlevels_isonmaxlevel%` | "yes" if player is at max level, else "no" |
| `%krakenlevels_isonmission%` | "yes" if a mission is active for the next level |
| `%krakenlevels_displaylevel%` | Display name of current level (from config) |
| `%krakenlevels_displaynextlevel%` | Display name of next level (from config) |
| `%krakenlevels_balance%` | Player balance (Vault required) |

## Notes
- The plugin is actively tested on LeafMC 1.21.X
- Older versions are not supported and won’t be backported (e.g., 1.19, 1.18, etc.)
- If you want add support for older versions, consider forking the project or contributing.

## Attribution

- Original plugin by Aglerr
- If you create a fork or a plugin based on this work, please include a clear mention of:
  - Aglerr as the original creator, and
  - This fork (KrakenLevels) as your base

Example mention: "Based on KrakenLevels (originally by Aglerr)"

## Contributing

Contributions are welcome! Feel free to open issues or pull requests.

## License

Licensed under AGPL-3.0. You must preserve copyright and attribution
notices, and make source changes available when publicly running the plugin.
