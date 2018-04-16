glowstone.yml
#############

The :code:`glowstone.yml` file allows you to edit your server settings.

This section documents the different options inside the file. We recommend using the navigation tree on the left
to move around.

server
======

Basic server settings.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| ip                             | text *(optional)* | *(Blank)*                      | Which interface the server should listen on, usually blank. |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| port                           | integer           | 25565                          | The port the server should listen on.                       |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| name                           | text              | Glowstone Server               | The server's name, used in queries.                         |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| log-file                       | text              | logs/log-%D.txt                | Where the log is stored relative to the server folder.      |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
|                                |                   |                                | Whether connecting players are authenticated.               |
| online-mode                    | true/false        | true                           | Only disable this if you know what you are doing.           |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| max-players                    | integer           | 20                             | The maximum number of players on the server.                |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| whitelisted                    | true/false        | false                          | Whether the whitelist is enabled.                           |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| motd                           | text              | Glowstone Server               | The message shown in the server list.                       |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| shutdown-message               | text              | Server shutting down.          | The message used to kick players when the server stops.     |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| allow-client-mods              | true/false        | true                           | Tell Forge clients whether or not the server allows         |
|                                |                   |                                | for client mods.                                            |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| snooper-enabled                | true/false        | false                          | Whether Minecraft stats reporting is enabled.               |
|                                |                   |                                | Currently not implemented.                                  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| prevent-proxy-connections      | true/false        | true                           | Whether the server should verify that the IP that is        |
|                                |                   |                                | used for connecting to the server is also used for          |
|                                |                   |                                | authenticating with the Mojang servers.                     |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

console
=======

Settings for the console (terminal) output.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| use-jline                      | true/false        | true                           | Whether the fancy console is enabled.                       |
|                                |                   |                                | Disable if you're having console problems.                  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| prompt                         | text              | :code:`'> '`                   | The console prompt that appears before the input field.     |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| date-format                    | text              | HH:mm:ss                       | How the time and date are displayed within the console.     |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| log-date-format                | text              | yyyy/MM/dd HH:mm:ss            | How the time and date are logged in the log files.          |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

game
====

Settings for in-game features.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| gamemode                       | text *(enum)*     | SURVIVAL                       | The default gamemode, one of                                |
|                                |                   |                                | SURVIVAL, CREATIVE, ADVENTURE, or SPECTATOR.                |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| gamemode-force                 | true/false        | false                          | Whether players are forced to the default gamemode on join. |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| difficulty                     | text *(enum)*     | NORMAL                         | The difficulty, one of                                      |
|                                |                   |                                | PEACEFUL, EASY, NORMAL, or HARD.                            |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| hardcore                       | true/false        | false                          | Whether hardcore mode (ban on death) is enabled.            |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| pvp                            | true/false        | true                           | Whether player vs. player mode is enabled.                  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| max-build-height               | integer           | 256                            | The maximum height at which players may build.              |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| announce-achievements          | true/false        | true                           | Whether achievements are announced in the chat. Unused.     |
| *(deprecated)*                 |                   |                                |                                                             |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| allow-flight                   | true/false        | false                          | Whether unauthorized flight prevention is disabled.         |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| command-blocks                 | true/false        | false                          | Whether command blocks are enabled. Unused.                 |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| resource-pack                  | text *(optional)* | *(Blank)*                      | The URL of the resource pack to send to clients by default. |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| resource-pack-hash             | text *(optional)* | *(Blank)*                      | The hash of the resource pack for data integrity purposes.  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

world
=====

Used to choose how the default worlds are configured.
For advanced world configuration, a plugin such as Multiverse may be appropriate.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| name                           | text              | world                          | The name of the main world.                                 |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| seed                           | text *(optional)* | *(Blank)*                      | The seed to use for the main world, or blank for random.    |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| level-type                     | text *(enum)*     | DEFAULT                        | The world type to use for the main world, one of            |
|                                |                   |                                | DEFAULT, FLAT, DEFAULT_1_1, LARGEBIOMES, or AMPLIFIED.      |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| spawn-radius                   | integer           | 16                             | The radius around a world's spawn point to protect          |
|                                |                   |                                | from damage, or 0 to disable.                               |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| view-distance                  | integer           | 8                              | The radius of the area of chunks to send to players.        |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| gen-structures                 | true/false        | true                           | Whether structures (villages, strongholds, etc.) are        |
|                                |                   |                                | generated.                                                  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| allow-nether                   | true/false        | true                           | Whether a Nether world is created by default.               |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| allow-end                      | true/false        | true                           | Whether an End world is created by default.                 |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| keep-spawn-loaded              | true/false        | true                           | Whether chunks around world spawns are kept                 |
|                                |                   |                                | loaded by default.                                          |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| populate-anchored-chunks       | true/false        | false                          | Whether anchored chunks, like world spawns, are             |
|                                |                   |                                | populated as soon as they are loaded. False means           |
|                                |                   |                                | that these chunks will wait to be populated until a         |
|                                |                   |                                | player loads those chunks for the first time, resulting     |
|                                |                   |                                | in a long "Downloading terrain" wait time, and server       |
|                                |                   |                                | stutter on first world join.                                |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| classic-style-water            | true/false        | false                          | Changes the water flow behavior to be finite with a         |
|                                |                   |                                | moving source.                                              |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| disable-generation             | true/false        | false                          | Disables world generation.                                  |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

