Install Glowstone
=================

1. Download the latest build of Glowstone_.
2. Move the jar file to your server folder. If you drop and run the jar in your current server folder, it will automatically migrate most settings to Glowstone.
3. Follow the instructions for your operating system below.

.. _Glowstone: https://glowstone.net/#downloads

Windows
-------

Using a text editor like Notepad, create a new start script named :code:`start.bat` to launch the jar file:

.. code-block:: bat

    @echo off
    java -Xms768M -XX:+UseG1GC -jar glowstone.jar
    pause

Make sure you select :code:`All Files` as the file type in the save window.

Finally, double click the :code:`start.bat` file.

GNU/Linux
---------

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
-----

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
