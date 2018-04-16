Basic Administration
====================

Administration tasks are done through commands, either inside the console (the terminal) or by players (in-game).
These commands are used in the form :code:`<command> [arguments...]`.

When describing a command, words inside angled brackets (:code:`<...>`) represent **required** arguments, while square
brackets (:code:`[...]`) represent **optional** arguments.

.. note::

    When using commands in-game, the forward-slash prefix (:code:`/`) is added.

    For example, a player would use :code:`/kick otherplayer You are evil`, while the console operator would use
    :code:`kick otherplayer You are evil`.

    For the sake of consistency, the prefix will not be used in this documentation.

Operators
---------

In order to give permission to a player to use administration commands, they will need to be made **operators** of the server.

A player can be added as a server operator using the :code:`op <player>` command. For example, to add a player named "glowstoner" as an operator,
use the command :code:`op glowstoner`.

Similarly, to remove a player as an operator, use :code:`deop <player>`. For example, :code:`deop glowstoner`.

Players that attempt to use administrative commands without operator privileges will receive an error.

Kicking and Banning Players
---------------------------

In order to kick a player from the server, use the :code:`kick <player> [reason]` command. The first argument
is the name of the target player, and is required. The remainder of the command is optional and will be shown
to the kicked player.

For example, :code:`kick glowstoner Not today!` would show "Not today!" on `glowstoner`'s client.

Kicking a player is considered a "temporary" punishment, because the player can still log back into the server after
being disconnected. In order to **ban** a player from joining the server, use the similar :code:`ban <player> [reason]` command.

In order to un-ban a player, use the :code:`pardon <player>` command.

Whitelisting
------------

Whitelisting allows you to limit which players can join the server. When enabled, players not on the whitelist will
not be able to join the server.

In order to enable the whitelist, use the :code:`whitelist on` command. Similarly, use :code:`whitelist off` to
disable it.

To add a player to the whitelist, use :code:`whitelist add <player>`. Oppositely, use :code:`whitelist remove <player>`
to remove them.

Operators can list players currently inside the whitelist using :code:`whitelist list`.