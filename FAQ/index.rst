Frequently Asked Questions
##########################

This is a list of questions that come up a lot.
We hope to be able to provide answers to these oft-asked questions here.
If you feel that we're missing a question, you can submit an issue.

.. tip::

    There is a lot of information on this page, we recommend using the navigation tree on the left to move around.

If you've gone through this page and still can't find the answer to your question,
you may `create a new ticket`_ with your problem, or join us on Discord_ and talk to someone directly.
If you decide to do the latter, please remember that people are busy and may take some time to respond.

.. _Discord: https://discord.gg/TFJqhsC
.. _create a new ticket: https://github.com/GlowstoneMC/Glowstone/issues/new

Legal
=====

.. warning::

    **We are not lawyers, we're programmers.**

    You should use the information pertaining to this section as a guideline, rather than a basis for your legal arguments in court.

If I use Glowstone, do I still have to follow the EULA\?
---------------------------------------------------------

**Yes, you still have to follow the Minecraft EULA.**

Glowstone is a Minecraft server - that is to say, it implements the Minecraft protocol,
is designed to work with Minecraft clients, and allows users to play Minecraft with other users.
Anyone that plays Minecraft in any capacity or runs a service that works with Minecraft players
is required to follow the `Minecraft EULA`_. See *Blizzard v bnetd*.

If you feel that this is incorrect, we suggest that you seek professional legal counsel before inadvertently breaking the EULA.

.. _Minecraft EULA: https://account.mojang.com/documents/minecraft_eula

Errors
======

Failed to bind to address. Maybe it is already in use?
------------------------------------------------------

.. code-block:: none

    [SEVERE] Error during server startup.
    java.lang.RuntimeException: Failed to bind to address. Maybe it is already in use?
            at net.glowstone.GlowServer.bind(GlowServer.java:438)
            at net.glowstone.GlowServer.main(GlowServer.java:93)

**This error means that you've already got a server running on the port that you've configured.**

More information can be found in the :ref:`Server Binding` subsection inside the First Run section.

Unsupported major.minor version
-------------------------------

.. code-block:: none

    Exception in thread "main" java.lang.UnsupportedClassVersionError: net/glowstone/GlowServer : Unsupported major.minor version 52.0


**This error means that you're running a Java version older than Java 8, and you'll need to update.**
On Windows and Linux, this should be fairly self-explanatory, but macOS users may find that they've already upgraded Java.
If you use macOS, then you should follow `this excellent guide`_.

.. _this excellent guide: https://gist.github.com/johan/10590467

java.lang.ClassNotFoundException: net.minecraft.server or org.bukkit.craftbukkit
--------------------------------------------------------------------------------

.. code-block:: none

    [SEVERE] Could not load 'plugins/MassiveCore.jar' in folder 'plugins'
        org.bukkit.plugin.InvalidPluginException: java.lang.NoClassDefFoundError: net/minecraft/server/v1_7_R4/PlayerInventory

This error is caused by plugins whose developers refused or were unable to use pure Bukkit classes when writing their plugins,
and instead used CraftBukkit or internal Minecraft classes to achieve the functionality they needed.

These plugins are often called "impure" plugins, and aren't technically Bukkit plugins at all.
**They will not work with Glowstone.** You will have to ask the developer of the plugin to add Glowstone support, or fix the plugin yourself, if you're able to.

Plugins that rely on ProtocolLib will also have the same issue, as it uses internal Minecraft classes.



Inconsistencies
===============

[Insert feature here] doesn't work!
-----------------------------------

Glowstone is a completely custom server software - that means that it does not use any of the Minecraft code.
CraftBukkit (commonly known as Bukkit) heavily used internal Minecraft code for a lot of the things that it does.

As Glowstone doesn't, and can't, use the relevant Minecraft code for anything it implements,
all of the features you'd expect from a Minecraft server must be rewritten from scratch.

As a result, Glowstone development is a little slow for some people's tastes,
and leaves many new users somewhat confused. While we are working to be a complete Minecraft server replacement,
these things take time.

I used the same world seed on [Platform], but Glowstone's world looks different
-------------------------------------------------------------------------------

Because our terrain generator was made from scratch, using the same seed with another platform will not generate the same terrain
(and may actually be completely different!). This is an expected caveat from a from-scratch implementation,
because of how pseudo-randomization works.



Frequently Asked Features
=========================

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