.. oTree Manager documentation master file, created by
   sphinx-quickstart on Wed Sep 26 09:33:15 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

oTree Manager
=============

*Note: Development of oTree Manager has ended. Sub-domain hosting and wildcard SSL certificated proved difficult in university IT systems. Reverse proxying subpaths (example.com/otree1) to container instances appears to be impossible at this time due to some hard-coded oTree url routing.*

Features
^^^^^^^^
- create and manage fully independent, production-ready oTree instances
- intuitive web interface for lab managers and experimenters
- Heroku-ish deployment of experiments with Git
- easy to remember URLs, no manual port configuration
- automatic configuration of PostgreSQL, Redis, and environment variables for production
- written in Python, built on industry standards (Docker, Dokku, Django)
- less resource intensive than virtual machine setups
- Lobby feature for easy experiment administration


Code
^^^^
https://github.com/otree-manager/otree_manager


.. toctree::
   :maxdepth: 2
   :caption: Contents:

   user.rst
   admin.rst
   install.rst

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

