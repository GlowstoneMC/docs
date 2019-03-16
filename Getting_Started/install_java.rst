Install Java
============

Install `OpenJDK 8`_ (recommended).
If you're running a Linux distro, look into installing OpenJDK through your package manager before using these downloads.

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


.. _OpenJDK: http://openjdk.java.net/install/
.. _this guide: https://gist.github.com/johan/10590467
