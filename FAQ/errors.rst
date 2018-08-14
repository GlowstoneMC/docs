Errors
######

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