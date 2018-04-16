First Run
#########

After having installed Glowstone for your operating system, you can start your server using the script you created.

.. tip::

    If you want the server to simply generate/validate configuration files without starting the server, you can use the
    :code:`--generate-config` command-line argument.

    Simply add the argument at the end of the :code:`java [...] -jar glowstone.jar` line inside your startup script.

Console Output
==============

Server Version
--------------

Whenever you start the server, the first line will output the server version. For example:

.. code-block:: none

    [INFO] This server is running Glowstone version 2018.4.0-SNAPSHOT.be008ff (MC: 1.12.2) (Implementing API version 1.12.2-R2.1-SNAPSHOT)

* The first information is the software version, :code:`2018.4.0-SNAPSHOT`. The :code:`SNAPSHOT` suffix is only present on development versions (i.e. not releases).
* The second part is a hash segment uniquely identifying the build you are using (:code:`be008ff`).
* In parentheses is the Minecraft version supported by the server (:code:`MC: 1.12.2`).
* Finally, the API version is the Glowkit_ version the server implements (:code:`1.12.2-R2.1-SNAPSHOT`).

.. _Glowkit: https://github.com/GlowstoneMC/Glowkit

Library Downloads
-----------------

When you first start the server, it will need to download some additional libraries from our repository
in order to keep compatibility with some plugins. This may take a few seconds depending on your internet connection.

.. code-block:: none

    [INFO] Downloading org.apache.commons:commons-lang3:3.5...
    [INFO] Downloaded org.apache.commons:commons-lang3:3.5.
           [ etc. ]

More information about libraries can be found in the `Library Management`_ section.

Plugin Scanning
---------------

Your server will then scan for plugins inside the :code:`plugins` directory. Once it finds compatible plugins,
they will be loaded before the worlds are loaded. If you are familiar with Bukkit plugin development, this is
the time when the :code:`JavaPlugin#onLoad()` method is executed.

World Generation/Loading
------------------------

The server will load world files from disk, located by default in the :code:`worlds` directory.
If it can't find a world, it will create it and start generating the terrain. Again,
this may take a while depending on your hardware.

.. code-block:: none

    [INFO] Preparing spawn for world...
    [INFO] Preparing spawn for world: 0%
    [INFO] Preparing spawn for world: 2%
    [INFO] Preparing spawn for world: 6%
           [ etc. ]
    [INFO] Preparing spawn for world: done

Plugin Enabling
---------------

After the worlds are loaded and ready, the plugins that were previously loaded are now "enabled".

Server Binding
--------------

Once it is ready, the server will open itself on a TCP port. By default, this is port :code:`25565`, and can be
changed in the server configuration. For more information, refer to the :doc:`../Configuration_Guide/index` section.

.. code-block:: none

    [INFO] Binding server to 0.0.0.0:25565...
    [INFO] Successfully bound server to 0.0.0.0:25565.
    [INFO] Ready for connections.

Once the "Ready for connections." line is output, your server should be reachable by clients.

.. error::

    **Failed to bind to address. Maybe it is already in use?**

    This error means that you've already got a server running on the port that you've configured.

    When starting the server, please make sure you do so by following the methods in the installation instructions, instead of double-clicking the JAR.
    If you do double-click the JAR, the server will start up, but you won't have any console,
    so you'll have to kill it using the `task manager`_ or whatever process management tools are relevant to your system.

    * If you're converting from Bukkit, make sure you've stopped the old Bukkit server, if you plan to use the same port.

        * Make sure you're not running more than one copy of Glowstone on the same port.
        * Check that you have no extra Java processes running. If you're on Windows, use the `Task Manager`_. You might not want to kill some of them, such as the Minecraft client.
        * If this still isn't working, please check whether you have an :code:`ip` set in the :code:`server` section of your :code:`config/glowstone.yml` file.

            * If you do, please consider that most people will not need this entry - it's only useful for people running large servers with multiple network cards. In the majority of cases, you can simply remove this line from your file.
            * If you're convinced that you need it, it should contain only an IP address - usually of the form :code:`a.b.c.d`, from :code:`0.0.0.0` up to :code:`255.255.255.255` for IPv4.

    .. _task manager: http://i.imgur.com/qWU4qVg.png
