==================
Django Travis Demo
==================

.. image:: https://secure.travis-ci.org/visualspace/django-travis-demo.png?branch=master
    :target: http://travis-ci.org/visualspace/django-travis-demo

Example of how to use `Travis CI <https://travis-ci.org/>`_ to automatically
run tests for Django pluggable apps using
`django-setuptest <https://github.com/praekelt/django-setuptest>`_.

Lazy people: GO HERE
--------------------
If you've got an existing Django app with tests, you can cherry-pick from
this repository in order to make them work with Travis CI. However, prepare
to manually merge changes to `setup.py` in::

	git fetch https://github.com/visualspace/django-travis-demo.git
	git cherry-pick 0333f23014dbd5ada22d4cacc079331d889afa29
	git cherry-pick 7e96de8e8cd60351c736ee884a5a3b748eb59547

After this, check and edit `setup.py` and `test_settings.py`, enable Travis
for the package, push and you *should* see your tests being run.

General overview
----------------
The steps to replicate this work are (roughly) as follows:

#. Create GIT repo::
   	git init django-appname
#. Create Django app and add to repo::
   	django-admin.py startapp appname
#. Add `setup.py`, see
   `Building and Distributing Packages with Distribute <http://packages.python.org/distribute/setuptools.html>`_
#. Add `django-setuptest <https://github.com/praekelt/django-setuptest>`_ to
   `setup.py` and add create `test_settings.py`. See `0333f2 <https://github.com/visualspace/django-travis-demo/commit/0333f23014dbd5ada22d4cacc079331d889afa29>`_.
#. Add `.travis.yml <http://about.travis-ci.org/docs/user/build-configuration/>`_ file, see `7e96de <https://github.com/visualspace/django-travis-demo/commit/7e96de8e8cd60351c736ee884a5a3b748eb59547>`_.
#. Add Travis `build status <http://about.travis-ci.org/docs/user/status-images/>`_
   image to README.
#. Enable the app for testing with Travis on the Travis `profile page <https://travis-ci.org/profile/>`_.
#. Push everything to GitHub.
#. Watch your app's tests being run by Travis on several Python and Django
   versions.
