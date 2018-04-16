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
changed in the server configuration. For more information, refer to the `Configuration Guide`_ section.

.. code-block:: none

    [INFO] Binding server to 0.0.0.0:25565...
    [INFO] Successfully bound server to 0.0.0.0:25565.
    [INFO] Ready for connections.

Once the "Ready for connections." line is output, your server should be reachable by clients.