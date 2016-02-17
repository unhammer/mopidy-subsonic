***************
Mopidy-Subsonic
***************

.. image:: https://pypip.in/v/Mopidy-Subsonic/badge.png
    :target: https://pypi.python.org/pypi/Mopidy-Subsonic/
    :alt: Latest PyPI version

.. image:: https://pypip.in/d/Mopidy-Subsonic/badge.png
    :target: https://pypi.python.org/pypi/Mopidy-Subsonic/
    :alt: Number of PyPI downloads


`Mopidy <http://www.mopidy.com/>`_ extension for playing music from
`Subsonic <http://www.subsonic.org/>`_.


Installation
============

Install by running::

    sudo pip install mopidy-subsonic

Or, if available, install the Debian/Ubuntu package from `apt.mopidy.com
<http://apt.mopidy.com/>`_.


Configuration
=============

Before starting Mopidy, you must tell it where to find Subsonic by adding the
following to your Mopidy configuration::

    [subsonic]
    hostname = some.website.com (leave off http/https)
    port = 8888
    username = USER
    password = PASS
    ssl = (yes/no)
    context = my-subsonic (if your subsonic is accessible on http://some.website.com:8888/my-subsonic/index.view)

Searches in Mopidy will now return results from your Subsonic library.

If you have no context, use `/`.

If you want to use hostname that redirects to your dynamic IP, you should use the port/ssl-setting of the initial hostname. So if your site uses port 8443 and SSL, but you want to use the redirect from your subsonic.org subdomain, you would do something like::

    [subsonic]
    hostname = SUBDOMAIN.subsonic.org
    port = 80
    ssl = no
    context = /
    username = USER
    password = PASS

Project resources
=================

- `Source code <https://github.com/rattboi/mopidy-subsonic>`_
- `Issue tracker <https://github.com/rattboi/mopidy-subsonic/issues>`_
- `Download development snapshot <https://github.com/rattboi/mopidy-subsonic/tarball/master#egg={{ cookiecutter.dist_name }}-dev>`_


Changelog
=========

v1.0.0 (UNRELEASED)
-------------------

- Require Mopidy >= 1.0

- Update to work with new playback API in Mopidy 1.0

- Update to work with new search API in Mopidy 1.0

v0.3.1 (2014-01-28)
-------------------

- Removed last_modified field from Playlist generation, to avoid problem in Mopidy core

v0.3 (2014-01-19)
-----------------

- Require Mopidy >= 0.18.

- Fixed: ``ext.conf`` was missing from the PyPI package, stopping Mopidy from
  working as long as Mopidy-Subsonic is installed.

v0.2 (2013-11-13)
-----------------

- Fixed: Crash when starting Mopidy-Subsonic with zero playlists on server

v0.1 (2013-08-29)
-----------------

- Initial release.
