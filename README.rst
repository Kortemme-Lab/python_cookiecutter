******************
cookiecutter_pyapp
******************

A cookiecutter template for python applications.  See 
https://github.com/audreyr/cookiecutter.  This cookiecutter will::

1. Create a ``setup.py`` file that's immediately ready to use.

2. Create a ready-to-use Sphinx directory for documentation.

3. Create an ``__init__.py`` with ``__version__`` filled in.

4. Copy the GPLv3 license text into the project.

5. Create a ``git`` repository and make an initial commit.

Making a new application
========================
Just give ``cookiecutter`` the path to this repository and answer all of its 
questions::

   cookiecutter https://github.com/kalekundert/cookiecutter_pyapp.git

If you find yourself using this cookiecutter a lot, you can save yourself some 
typing by aliasing it in your ``~/.cookiecutterrc`` file::

   abbreviations:
       pyapp: https://github.com/kalekundert/cookiecutter_pyapp.git

Publishing to PyPI
==================
When you want to publish a version of your application to PyPI, the first step 
is to increment the version number stored in ``__init__.py`` and to commit that 
with a tag that matches the new version.  You can do using the ``bumpversion`` 
command (pre-installed in the virtual environment) to do this automatically::

   $ bumpversion major
   $ bumpversion minor
   $ bumpversion patch

The next step is to upload your project.  If you haven't already registered 
your project, run this command before anything else::

   $ python setup.py register

This command will ask for your PyPI login credentials unless you've already 
provided them in your ``~/.pypirc`` file, which is probably worthwhile if 
you're creating enough new project to warrant using ``cookiecutter``.  Once 
your project is registered, upload it with the following command::

   $ python setup.py sdist upload

Not Exactly What You Want?
==========================
If you have differences in your preferred setup, I encourage you to fork this
to create your own version.  Or create your own; it doesn't strictly have to
be a fork.  It's up to you whether or not to rename your fork/own version. Do 
whatever you think sounds good.  I'll also accept pull requests if they're 
small, atomic, and if they make my own development experience better.

.. _Travis-CI: http://travis-ci.org/
.. _Sphinx: http://sphinx-doc.org/
.. _ReadTheDocs: https://readthedocs.org/
