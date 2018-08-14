Contributing to Docs
####################

This is a guide on how to setup your environment to write docs for this website.


We really appreciate users and developers contributing to our documentation!

Setup
=====

System Requirements
-------------------

In order to edit and build docs locally, you will need to have the following:

- Git
- Python 3.6.x
- Pipenv
- **Linux and Mac**: The ``make`` CLI

If you've never used Pipenv before, it is a useful tool to create Python virtual environments. You can get it
using ``pip`` for your Python 3.6 environment:


.. code-block:: sh

    python3.6 -m pip install pipenv

Local Docs Setup
----------------

First, create an account on GitHub, and fork the Glowstone docs repository to your account.

Then, clone your fork locally using:

.. code-block:: sh

    git clone https://github.com/[your_username]/docs.git Glowstone-Docs

Switch to the directory that was created (``cd Glowstone-Docs``), then run the following to
install the required dependencies:

.. code-block:: sh

    pipenv sync --dev

Finally, create a branch for your changes. The name of the branch can describe what your changes are about.

.. code-block:: sh

    git checkout -b my-branch-name

Editing Docs
------------

Once your environment is setup, you can now modify the RST files inside of the repository.

To build docs, run ``make html``. The files will be output in the ``_build/html`` directory.

Sometimes, it might be necessary to do a complete re-build of the project.
To do so, run ``make clean``, and then ``make html``.


Submitting Changes
------------------

First, you will need to commit your changes. To do so, add your changes using ``git add .``. Then, commit using:

.. code-block:: sh

    git commit -m "A message describing your changes"

Finally, push your commit(s) to your fork using:

.. code-block:: sh

    # "my-branch-name" should correspond to the name of your local branch
    git push -u origin my-branch-name

Once your changes have been pushed, you can create a Pull Request by
viewing your branch on GitHub and clicking on "Pull Request".
