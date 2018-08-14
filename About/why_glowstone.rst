Why Glowstone
#######################

**Glowstone is completely open-source**. We do not depend on internal Minecraft code, all of it is original.
This also means our code is a lot simpler and much more optimized in most places than CraftBukkit and Minecraft.

Just because Glowstone is written from scratch does not mean you'll sacrifice plugin compatibility.
Glowstone supports Bukkit, Spigot-API, and Paper-API plugins natively.

If you are a developer, you will find contributing a lot easier than with CraftBukkit, as there is no obfuscated code
or a need to maintain a minimal diff. You could even modify Glowstone for private use, to strip away or enhance
parts of Glowstone to your server's specific needs.

.. note::

    We would like to say that Glowstone is not complete, and you will notice some missing features compared
    to your CraftBukkit-based server.

    We also do not support "*NMS*" or "*OBC*" code, although enhanced compatibility
    is being worked on through Linkstone_. In other words, Glowstone does not provide :code:`org.bukkit.craftbukkit.*`
    and :code:`net.minecraft.server.*` packages, so **plugins using these packages will break**.

.. _Linkstone: https://github.com/GlowstoneMC/Linkstone
