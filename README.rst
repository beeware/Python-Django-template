Python Django Template
======================

A template for building Python apps that will run as a web server using Django.

This repository branch contains a template for Python 3.5. Other Python versions are available by cloning other branches of repository.

How to use
------------

Create a `setup.py`::


  #!/usr/bin/env python

  from setuptools import setup, find_packages

  setup(name='YourProject',
      version = '0.1',
      packages = find_packages(),
      options = {
          'app': {
              'formal_name': 'Your Project',
          },
          'django': {
              'app_requires': [
                  'toga-django',
                  'toga'
              ]
          }
      } 
  )


Create a Python 3.5 ``virtualenv``, and ``pip install briefcase``

Then, generate the template::

  python setup.py django
