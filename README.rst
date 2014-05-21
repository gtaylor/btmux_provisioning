Basic BattletechMUX Provisioning
================================

This repository contains everything needed to get a quick and dirty instance
of BattletechMUX running. It will pull the latest stable branch from git,
configure/compile the source, and present you with a game running on port
5555 of a VM running at 192.168.111.111.

The following components are used:

* `Vagrant`_ - Used to run btmux on a local VM.
* `Ansible`_ - Provisioning of local or remote gamess.
* `VirtualBox`_ - Virtualization software used by Vagrant (local only).

Getting started
---------------

Create a Python virtualenv and install the requirements::

    pip install -r requirements.txt

After that, fire up vagrant::

    vagrant up

After that, you should be able to reach your game::

    telnet 192.168.111.111 5555

.. _Ansible: http://www.ansibleworks.com/
.. _Vagrant: http://www.vagrantup.com/
.. _VirtualBox: https://www.virtualbox.org/
