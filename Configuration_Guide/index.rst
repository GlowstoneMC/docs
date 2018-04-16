Configuration Guide
###################

The YAML files allow you to edit your server settings.
They can be found in the :code:`config` directory in your server installation.

After modifying your configuration files, you will need to restart your server to apply the changes.

.. tip::

    If you want the server to simply generate/validate configuration files without starting the server, you can use the
    :code:`--generate-config` command-line argument.

    Simply add the argument at the end of the :code:`java [...] -jar glowstone.jar` line inside your startup script.

.. toctree::
    :maxdepth: 2
    :caption: Contents
    :titlesonly:

    glowstone_yml/index
