Python Linux Template
=====================

A template for building Python apps that will run under Linux.

**This repository branch contains a template for Python 3.6**.
Other Python versions are available by cloning other branches of repository.

Using this template
-------------------

The easiest way to use this project is to not use it at all - at least,
not directly. `Briefcase <https://github.com/pybee/briefcase/>`__ is a
tool that uses this template, rolling it out using data extracted from
your ``setup.py``.

However, if you *do* want use this template directly...

1. Install `cookiecutter`_. This is a tool used to bootstrap complex project
   templates::

    $ pip install cookiecutter

2. Run ``cookiecutter`` on the Python-Linux template::

    $ cookiecutter https://github.com/pybee/Python-Linux-template --checkout 3.6

3. Add your code to the template. At the very minimum, you need to have an
   ``app/<app name>/__main__.py`` file that defines an entry point that
   will start your application. If ``<app name>`` contains a dash, it will be
   converted to an underscore in the expected package name

   If your code has any dependencies, they should be installed under the
   ``app_packages`` directory.


If you've done this correctly, a project with a formal name of ``My Project``,
with an app name of ```my-project`` should have a directory structure that
looks something like::

    My Project/
        app/
            my_project/
                __init__.py
                __main__.py
        app_packages/
            ...
        myproject

Next steps
----------

Of course, just running Python code isn't very interesting by itself - you'll
be able to output to the console, and see that output in XCode, but if you
tap the app icon on your phone, you won't see anything - because there isn't a
visible console on an iPhone.

To do something interesting, you'll need to work with the native system
libraries to draw widgets and respond to screen taps. You could use the
`toga`_ library to provides a cross-platform widget toolkit that supports
Linux (using GTK+).

If you have any external library dependencies (like ``toga``, or anything other
third-party library), you should install the library code into the
``app_packages`` directory. This directory is the same as a  ``site_packages``
directory on a normal Python install.

.. _cookiecutter: http://github.com/audreyr/cookiecutter
.. _toga: http://pybee.org/toga
