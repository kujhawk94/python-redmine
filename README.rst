Python-Redmine
==============

.. image:: https://badge.fury.io/py/python-redmine.svg
   :target: https://badge.fury.io/py/python-redmine

.. image:: https://img.shields.io/travis/com/maxtepkeev/python-redmine/master
   :target: https://app.travis-ci.com/maxtepkeev/python-redmine

.. image:: https://img.shields.io/coverallsCoverage/github/maxtepkeev/python-redmine?branch=master
   :target: https://coveralls.io/github/maxtepkeev/python-redmine?branch=master

Python-Redmine is a library for communicating with a `Redmine <http://www.redmine.org>`__
project management application. Redmine exposes some of its data via `REST API
<http://www.redmine.org/projects/redmine/wiki/Rest_api>`__ for which Python-Redmine provides
a simple but powerful Pythonic API inspired by a well-known `Django ORM
<https://docs.djangoproject.com/en/dev/topics/db/queries/>`__:

.. code-block:: python

   >>> from redminelib import Redmine

   >>> redmine = Redmine('http://demo.redmine.org', username='foo', password='bar')
   >>> project = redmine.project.get('vacation')

   >>> project.id
   30404

   >>> project.identifier
   'vacation'

   >>> project.created_on
   datetime.datetime(2013, 12, 31, 13, 27, 47)

   >>> project.issues
   <redminelib.resultsets.ResourceSet object with Issue resources>

   >>> project.issues[0]
   <redminelib.resources.Issue #34441 "Vacation">

   >>> dir(project.issues[0])
   ['assigned_to', 'author', 'created_on', 'description', 'done_ratio',
   'due_date', 'estimated_hours', 'id', 'priority', 'project', 'relations',
   'start_date', 'status', 'subject', 'time_entries', 'tracker', 'updated_on']

   >>> project.issues[0].subject
   'Vacation'

   >>> project.issues[0].time_entries
   <redminelib.resultsets.ResourceSet object with TimeEntry resources>

Features
--------

* Supports 100% of Redmine API
* Supports external Redmine plugins API
* Supports Python 3.7 - 3.11 and PyPy3
* Supports different request engines
* Extendable via custom resources and custom request engines
* Extensively documented
* Provides ORM-style Pythonic API
* And many more...

Installation
------------

Standard Edition
++++++++++++++++

The recommended way to install is from Python Package Index (PyPI) with `pip <http://www.pip-installer.org>`__:

.. code-block:: bash

   $ pip install python-redmine

Pro Edition
+++++++++++

License for a Pro Edition can be bought
`here <https://secure.2checkout.com/order/checkout.php?PRODS=4708754&QTY=1&CART=1&CARD=1&DISABLE_SHORT_FORM_MOBILE=1>`__.
You will receive an email with all the details regarding Pro Edition installation process.

Documentation
-------------

Documentation is available at https://python-redmine.com.

Contacts and Support
--------------------

Support for Standard Edition is provided via `GitHub <https://github.com/maxtepkeev/python-redmine/issues>`__
only, while support for Pro Edition is provided both via `GitHub <https://github.com/maxtepkeev/python-redmine/issues>`__
and support@python-redmine.com. Be sure to write from email that was specified during the purchase procedure.

Copyright and License
---------------------

Python-Redmine Standard Edition is licensed under Apache 2.0 license. Python-Redmine Pro Edition is licensed
under the Python-Redmine Pro Edition 1.0 license. Check the `License <https://python-redmine.com/license.html>`__
for details.
