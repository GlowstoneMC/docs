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

creatures
=========

Used to control mob spawn limits.

.. note::

    Creature settings are not currently implemented, and are therefore not documented.


folders
=======

Settings for server folder names.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| plugins                        | text              | plugins                        | The plugins directory relative to server root.              |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| update                         | text              | update                         | The directory relative to 'plugins' to copy updates from    |
|                                |                   |                                | on startup.                                                 |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| worlds                         | text              | worlds                         | The world container relative to server root.                |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| libraries                      | text              | lib                            | The libraries directory relative to server root.            |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

files
=====

Settings for server file names. **These files are relative to the config directory.**

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| permissions                    | text              | permissions.yml                | The file to read custom permissions from.                   |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| commands                       | text              | commands.yml                   | The file to read command aliases from.                      |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| help                           | text              | help.yml                       | The file to read help topics from.                          |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

advanced
========

Advanced server configuration options.

+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| Key                                           | Type               | Default                        | Description                                                 |
+===============================================+====================+================================+=============================================================+
| connection-throttle                           | integer            | 4000                           | Time in milliseconds a client must wait before reconnecting.|
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| idle-timeout                                  | integer            | 0                              | How long until an idle (AFK) player is kicked (0 for never).|
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| warn-on-overload                              | true/false         | true                           | Whether to show warnings if the server is overloaded.       |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| exact-login-location                          | true/false         | false                          | Whether to skip fixing block collisions on player login.    |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| plugin-profiling                              | true/false         | false                          | Whether the :code:`timings` command is enabled.             |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| deprecated-verbose                            | true/false/default | false                          | Whether to always, never, or only sometimes show deprecation|
|                                               |                    |                                | warnings for plugins.                                       |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| compression-threshold                         | integer            | 256                            | The minimum packet size to compress. -1 to disable, 0 to    |
|                                               |                    |                                | compress everything.                                        |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| proxy-support                                 | true/false         | false                          | Whether proxy (e.g. BungeeCord) support is enabled, granting|
|                                               |                    |                                | access to the real IP and UUID of proxied players. Requires |
|                                               |                    |                                | the proxy to be configured correctly.                       |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| player-sample-count                           | integer            | 12                             | How many online players can be shown in the server list.    |
+------------------+----------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
|                  | enable                     | true/false         | false                          | Whether GPU-based computations are enabled.                 |
| graphics-compute +----------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
|                  | use-any-device             | true/false         | false                          | Whether any device can be used for OpenCL computations.     |
+------------------+----------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
|                  | cache-size                 | integer            | 256                            | The region file cache size, in MB.                          |
| region-file      +----------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
|                  | compression                | true/false         | true                           | Whether region files should be compressed.                  |
+------------------+----------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| profile-lookup-timeout                        | integer            | 5                              | Timeout for Mojang profile lookups, in seconds.             |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| suggest-player-name-when-null-tab-completions | true/false         | true                           | Checks if player names should be suggested when a           |
|                                               |                    |                                | command returns null as their tab completion result.        |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+

extras
======

Extra services which Glowstone can optionally provide.

+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| Key                            | Type              | Default                        | Description                                                 |
+================================+===================+================================+=============================================================+
| query-enabled                  | true/false        | false                          | Whether the query_ server is enabled.                       |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| query-port                     | integer           | 25614                          | The port the query server runs on.                          |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| query-plugins                  | true/false        | true                           | Whether the query response includes plugin info.            |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| rcon-enabled                   | true/false        | false                          | Whether the rcon_ server is enabled.                        |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| rcon-password                  | text              | glowstone                      | The rcon password.                                          |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| rcon-port                      | integer           | 25575                          | The port the rcon server runs on.                           |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+
| rcon-colors                    | true/false        | true                           | Whether the server should send color-codes to the           |
|                                |                   |                                | rcon client.                                                |
+--------------------------------+-------------------+--------------------------------+-------------------------------------------------------------+

.. _query: http://wiki.vg/Query
.. _rcon: http://wiki.vg/Rcon


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


libraries
=========

+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| Key                                           | Type               | Default                        | Description                                                 |
+===============================================+====================+================================+=============================================================+
| checksum-validation                           | true/false         | true                           | Whether downloaded libraries should be validated using their|
|                                               |                    |                                | checksum.                                                   |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| repository-url                                | text               | *Glowstone repo, see below*    | The repository URL to download libraries from.              |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| download-attempts                             | integer            | 2                              | The maximum amount of attempts to download each library.    |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| compatibility-bundle                          | text *(enum)*      | CRAFTBUKKIT                    | The compatibility bundle to use. Only CRAFTBUKKIT and NONE  |
|                                               |                    |                                | are supported. See the `Library Management`_ section.       |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+
| list                                          | list               | *Empty array*                  | A list of extra libraries to download on server startup.    |
|                                               | *(of libraries)*   |                                | See below for the content structure of this list.           |
+-----------------------------------------------+--------------------+--------------------------------+-------------------------------------------------------------+

**Note**: the default Glowstone library repository is :code:`https://repo.glowstone.net/service/local/repositories/central/content/`.

Library format
--------------

Each element of the library list (:code:`libraries.list` key) is an object with the following structure:

+-----------------------------------------------+--------------------+-------------------------------------------------------------+
| Key                                           | Type               | Description                                                 |
+===============================================+====================+=============================================================+
| group-id                                      | text               | The group ID of the library.                                |
+-----------------------------------------------+--------------------+-------------------------------------------------------------+
| artifact-id                                   | text               | The artifact ID of the library.                             |
+-----------------------------------------------+--------------------+-------------------------------------------------------------+
| version                                       | text               | The version of the library.                                 |
+-----------------------------------------------+--------------------+-------------------------------------------------------------+
| repository                                    | text *(optional)*  | If present, overrides the default repository URL.           |
+------------------+----------------------------+--------------------+-------------------------------------------------------------+
| checksum         | type                       | text *(enum)*      | The algorithm for the checksum. Only SHA-1 (:code:`sha1`)   |
| *(optional)*     |                            |                    | and MD5 (:code:`md5`) are supported.                        |
|                  +----------------------------+--------------------+-------------------------------------------------------------+
|                  | value                      | text               | The checksum of the library.                                |
+------------------+----------------------------+--------------------+-------------------------------------------------------------+

Again, more information about these fields and library management can be found in the `Library Management`_ section.