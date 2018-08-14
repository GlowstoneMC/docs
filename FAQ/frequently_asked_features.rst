Frequently Asked Features
#########################

Some features are frequently requested to us, and some will likely never be added officially.

Support for older versions
--------------------------

**We have taken the decision not to support older versions of Minecraft.**

We will always try to update to the latest Minecraft version once the Bukkit API is updated by the Spigot and Paper teams.
However, you may be able to achieve this by using third-party tools and plugins like BungeeCord_.
We have also worked with ProtocolSupport_'s team to make it possible to host older Minecraft versions on the latest version of Glowstone.

.. _BungeeCord: https://www.spigotmc.org/wiki/bungeecord/
.. _ProtocolSupport: https://github.com/ProtocolSupport/ProtocolSupport

Support for Sponge plugins
--------------------------

In the past, we have worked with the Sponge_ team to support the Sponge API on Glowstone.
Unfortunately, we have dropped this objective and we will likely never officially support Sponge plugins on our platform.
More details on this topic can be found here_.

.. _Sponge: https://www.spongepowered.org/
.. _here: https://forums.glowstone.net/topic/45/about-sponge

Support for Minecraft: Bedrock Edition
--------------------------------------

At this time, we simply do not have the time and resources to work on a Bedrock Edition port for Glowstone,
and we would rather focus our work on the PC version. Some third-party projects (like ProtocolSupport_)
are currently working on this kind of support on Bukkit platforms.

Packet API / ProtocolLib support
--------------------------------

Because networking is not part of the scope of the Bukkit API, there is no Packet API implementation in Glowstone.
We are faced with a decision between making our own API, or supporting an API designed by the community.
ProtocolLib_ has been around for quite a while and has become
the *de-facto* community standard API for packet handling.
ProtocolLib is designed to work on multiple versions of the Vanilla server using reflection,
but it does not support Glowstone networking internals.
This feature has been discussed on Github_, but it may take a while before anything is functional.

.. _ProtocolLib: https://github.com/dmulloy2/ProtocolLib/
.. _Github: https://github.com/dmulloy2/ProtocolLib/issues/308
