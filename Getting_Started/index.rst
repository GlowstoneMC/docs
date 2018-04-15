Getting Started
#######################

Glowstone Installation
************************

Installing Glowstone is as easy as installing any other server software.

Install Java
===============

Install `Oracle Java 8`_ (recommended).
If you're running a Linux distro, look into installing Oracle Java through your package manager before using these downloads.
But, if you really don't want Oracle Java, you can use OpenJDK_.

.. note::

    **We require Java 8 update 101 or greater.**
	
    Our Maven repository uses a Let's Encrypt HTTPS certificate, and Let's Encrypt was added to the Java truststore in update 101.
    
    Without this truststore, our library manager fails to pull dependencies from our server, due to an SSL security error.

Confirm that you have Java 8 by running :code:`java -version` in your system's command prompt/terminal.
You should see something like :code:`java version "1.8.0_121"` at the top. As long as it includes :code:`1.8`, and the number after the :code:`_` is more than 101, you're good.


.. note::

    If you installed Java 8 on **macOS**, but :code:`java -version` is showing an older version, run
	
    .. code-block:: sh

       sudo mv /usr/bin/java /usr/bin/java-1.6
       sudo ln -s '/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home/bin/java' /usr/bin/java


    For more details, see `this guide`_.


.. _Oracle Java 8: http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html
.. _OpenJDK: http://openjdk.java.net/install/
.. _this guide: https://gist.github.com/johan/10590467


Install Glowstone
====================

1. Download the latest build of Glowstone_.
2. Move the jar file to your server folder. If you drop and run the jar in your current server folder, it will automatically migrate most settings to Glowstone.
3. Follow the instructions for your operating system below.

.. _Glowstone: https://glowstone.net/#downloads

Windows
--------

Using a text editor like Notepad, create a new start script named :code:`start.bat` to launch the jar file:

.. code-block:: bat

    @echo off
    java -Xms768M -XX:+UseG1GC -jar glowstone.jar
    pause

Make sure you select :code:`All Files` as the file type in the save window.

Finally, double click the :code:`start.bat` file.

GNU/Linux
----------

Using a text editor like gedit, mousepad, Atom, Sublime Text, nano, (Neo)vi(m), Kate or emacs, create a new start script named :code:`start.sh` to launch the jar file:

.. code-block:: sh

    #!/bin/sh
    BINDIR=$(dirname "$(readlink -fn "$0")")
    cd "$BINDIR"
    java -Xms768M -XX:+UseG1GC -jar glowstone.jar

Open terminal, go to your Glowstone folder and enter this command to give the script execute permissions:

.. code-block:: sh

    chmod +x start.sh


Enter this command in the terminal to start the server:

.. code-block:: sh

    ./start.sh


macOS
------

Using a text editor like TextEdit, create a new start script named :code:`start.command` to launch the jar file:

.. code-block:: sh

    #!/bin/bash
    cd '$( dirname "$0" )'
    java -Xms768M -XX:+UseG1GC -jar glowstone.jar

Open terminal, change current directory by typing :code:`cd` and dragging and dropping the Glowstone folder into terminal window.

At this point it should look like this:

.. code-block:: sh

    cd /Users/YourName/YourGlowstoneFolder/Glowstone


If you think that is correct press enter and move to the next step.

Just **type** (do not enter!) this command to give the script execute permissions:

.. code-block:: sh

    chmod a+x


Drag start.command into the Terminal window. Confirm there is a space between :code:`chmod a+x` and the :code:`start.command` path, and then enter.
Finally, double click the :code:`start.command` file to start the server.


After Thoughts
================

If you have any trouble setting up, we would be happy to help you on the forums_
or Discord_. Otherwise, congratulations! You've just installed Glowstone!

* If you can't access your server from your public IP, make sure you have `port forwarded`_ or used a UPnP port mapper to allow incoming connections to your server.
* For server issues or suggestions, create an issue on Github.
* By default, all configuration files are in the :code:`config` folder.

.. _forums: https://forums.glowstone.net/
.. _Discord: https://discord.gg/TFJqhsC
.. _port forwarded: http://portforward.com/english/applications/port_forwarding/Minecraft_Server/

Plugins
************

Most Bukkit_, Spigot_ and Paper_ plugins will work on Glowstone.

.. warning::

    Plugins that use internals for Paper, Spigot, CraftBukkit, or Minecraft will not work, unless they are designed to fail gracefully.

    This includes plugins that use "*NMS*" reflectively.

.. _Bukkit: http://dev.bukkit.org/bukkit-plugins/
.. _Spigot: https://www.spigotmc.org/resources/categories/bukkit.4/
.. _Paper: https://aquifermc.org/resources/categories/server-plugins.2/
