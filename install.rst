Installation
============

Overview
^^^^^^^^
oTree Manager uses Docker to containerize both databases and the actual oTree installations. Container management is handled by Dokku. The web interfaces is written in Python (3) and builds upon Django in combination with Django-Channels for running background tasks. The web interface requires PostgreSQL and Redis databases to store its data and handle user sessions. Supervisor keeps the web interface as well as the background task worker running. Nginx serves as a reverse proxy for the oTree installations and handles routing of requests between the oTree instance containers and the web interface.

Currently, I only recommend installations on Debian-based operating systems and write the installation instructions for a fresh installation of Debian 9.

Note that Dokku, a core dependency, does not support macOS or Windows operating systems. Thus, oTree Manager cannot be installed on these systems either.

Intended Architecture
^^^^^^^^^^^^^^^^^^^^^
oTree Manager should not be installed on the typical experimenter's computer in the laboratory. It should be installed on its own dedicated workstation or server-grade hardware. This is because of multiple reasons. First, oTree Manager is intended to serve its web interface and oTree containers continuously '24/7'. Most consumer-grade hardware is not designed with this use case in mind. It is also typically not designed for virtualization-heavy workloads which require many CPU cores and large amounts of system memory for optimal performance. Second, setting up oTree Manager on its own machine provides a natural separation from existing legacy setups. That is, it can run in parallel to hardware required to support z-Tree and other experimental software tools. It can also be phased-in in parallel to current oTree setups. This reduces down-times and allows for a step-wise migration to the new system. A separate machine also has the advantage that security measures can be implemented more easily. With oTree Manager serving requests from the 'open' Internet, it is advisable to implement more stringent security (firewall) policies compared to typical lab computers, which often only serve locally. If in doubt, ask your university's IT department for assistance.

Installation
^^^^^^^^^^^^
Note: The installation instructions assume a clean Debian 9 installation to start from.

First, make sure to update all system packages to their latest versions and install git:

.. code-block::
   $ sudo apt update
   $ sudo apt upgrade
   $ sudo apt install git

Then, we install oTree Manager using its installation script:

.. code-block::
   $ git clone https://github.com/otree-manager/otree_manager_installation.git
   $ cd otree_manager_installation
   $ sudo bash ./otree_manager_setup.sh

Head over to GitHub to take a look at the installation script. https://github.com/otree-manager/otree_manager_installation