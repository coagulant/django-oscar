=====================
Sample Oscar projects
=====================

Oscar ships with two sample projects: a 'sandbox' site, which is a vanilla install of Oscar using the
default templates and styles, and a fully featured 'demo' site which demonstrates how Oscan can be
re-skinned and customised to model a domain. 

The sandbox site
----------------

The sandbox site is a minimal implementation of Oscar, where everything is left
in its default state.  It is useful for exploring Oscar's functionality
and developing new features.

It only has two customisations on top of Oscar's core:

* Two shipping methods are specified so that the shipping method step of
  checkout is not skipped.  If there is only one shipping method (which is true of core
  Oscar) then the shipping method step is skipped as there is no choice to be
  made.

* A profile class is specified which defines a few simple fields.  This is to
  demonstrate the account section of Oscar, which introspects the profile class
  to build a combined User and Profile form.

Note that some things are deliberately not implemented within core Oscar as they
are domain-specific.  For instance:

* All tax is set to zero
* No shipping methods are specified.  The default is free shipping.
* No payment is required to submit an order as part of the checkout process

The sandbox is, in effect, the blank canvas upon which you can build your site.

The demo site
-------------

The demo site is *the* reference Oscar project as it illustates how Oscar can be
redesigned and customised to build a e-commerce store.  The demo site is a
sailing store selling a range of different product types.

The customisations on top of core Oscar include:

* A new skin
* A variety of product types including books, clothing and downloads
* Payment with PayPal Express using django-oscar-paypal_.
* Payment with bankcards using Datacash using django-oscar-datacash_.

.. _django-oscar-paypal: https://github.com/tangentlabs/django-oscar-paypal
.. _django-oscar-datacash: https://github.com/tangentlabs/django-oscar-datacash

Browse the external sandbox site
================================

An instance of the sandbox site is build hourly from master branch and made
available at http://latest.oscarcommerce.com 

.. warning::
    
    It is possible for users to access the dashboard and edit the site content.
    Hence, the data can get quite messy.  It is periodically cleaned up.

Browse the external demo site
=============================

An instance of the demo site is built periodically (but not automatically) and
available at http://demo.oscarcommerce.com

Running the sandbox locally
===========================

It's pretty straightforward to get the sandbox site running locally so you can
play around with the source code.

Install Oscar and its dependencies within a virtualenv::

    $ git clone git@github.com:tangentlabs/django-oscar.git
    $ cd django-oscar
    $ mkvirtualenv oscar
    $ make sandbox
    $ sites/sandbox/manage.py runserver

The sandbox site (initialised with a sample set of products) will be available
at: http://localhost:8000.  A sample superuser is installed with credentials::

    username: superuser
    email: superuser@example.com
    password: testing

