=======================================
BUILDBOT CONTINUOUS INTEGRATION FOR CPS
=======================================

Build slave
===========

Install buildbot-buildslave in the standard way.

The buildslave must be able to create and update its testing instances in a
complete autonomous way, by issuing commands sent by the master.
You also need the needed test dependencies for XHTML and CSS validation.
TODO expand on that 

With official packages
----------------------
The simplest is to do it with the official packages.  At
the time of this writing, that implies to be on a Debian Lenny or
Squeeze, or an Ubuntu >= 10.04. You'll need:

- ``opt-zope-cps-VERSION-devsetup``, with
``VERSION`` being ``3.5`` or ``3.6``, according to your interests.
- ``opt-hgbundler``.

Manual installation
-------------------
You'll have to provide ``mkcpsdevinstance`` scripts in
``/opt/cps-VERSION/bin`` (``VERSION`` still being ``3.5`` or
``3.6``), with the same semantics as the ones of the Debian packages
(also currently available in ``Products/CPSUtil``).

For ``hgbundler``, put a clone in ``/opt/hgbundler`` and run buildout.

Hooking to buildbot.cps-cms.org
-------------------------------
Thank you for contributing your ressources to the CPS project !
Ask on the ``cps-devel`` mailing-list for registration, mentioning
the builders you'd be interested in and the name your slave should be
known as.

The master communication port is ``buildbot.cps-cms.org:9989``.

Master setups
=============
They work with the mercurial hook for PBChangeSource.
The simplest way is to create a new system user, have it own a mirror
of the hg repositories, and  put the hook registration and
configuration in that user's ``.hgrc``.

Generic CPS
-----------
Copy or link the ``master.cfg`` file to your freshly created buildbot master
Copy and adapt the ``credentials_conf.py.sample`` as ``credentials_conf.py``
and put alongside ``master.cfg``

Custom projects
-------------------
Copy or link the ``master_custom.cfg`` file to your freshly created
buildbot master.
Copy and adapt the ``credentials_conf.py.sample`` and
``custom_projects.py.sample`` as ``credentials_conf.py`` and
``custom_projects.py`` alongside ``master.cfg``.

.. Emacs
.. Local Variables:
.. mode: rst
.. End:
.. Vim
.. vim: set filetype=rst:
