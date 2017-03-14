Python Django Template
======================

A template for building Python apps that will run as a web server using Django.

This repository branch contains a template for Python 3.5. Other Python versions are available by cloning other branches of repository.

How to use
----------

Create a `setup.py`::


  #!/usr/bin/env python

  from setuptools import setup, find_packages

  setup(name='yourproject',
      version = '0.1.0',
      packages = find_packages(),
      options = {
          'app': {
              'formal_name': 'Your Project',
          },
          'django': {
              'app_requires': [
                  'toga-django',
              ]
          }
      }
  )

.. note::

    The version number must be compliant with `Semantic Versioning`_.
    Version numbers like ``"1.0"`` or ``"0.1"`` will be rejected
    by `npm` during the packaging of Javascript resources.

.. _Semantic Versioning: http://semver.org>

Create a Python 3.5 ``virtualenv``, and ``pip install briefcase``

Then, generate the template::

  $ python setup.py django

This will roll out a full Django project structure, expecting to find
a class called ``yourproject.app.YourProject`` that has a ``urls`` attribute.

Once you've rolled out the template, you'll need to do three
pieces of configuration:

1. Update the settings to reflect local conditions. Some default settings
   have been provided; to use them::

     $ cd django/briefcase/settings
     $ mv env.template .env
     $ cd ../..

   This will create a Sqlite database. If you want to use a different database
   configuration, you can edit the ``.env`` file (or any other settings file)

2. Run the initial migrations::

     $ ./manage.py migrate

3. Start the server::

     $ ./manage.py runserver
