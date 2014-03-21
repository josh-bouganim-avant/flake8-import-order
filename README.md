flake8-import-order
===================

[![Build
Status](https://travis-ci.org/public/flake8-import-order.png?branch=master)](https://travis-ci.org/public/flake8-import-order)

A [flake8](http://flake8.readthedocs.org/en/latest/) and
[Pylama](https://github.com/klen/pylama) plugin that checks the ordering of
your imports matches the [Google Style
Guidelines](http://google-styleguide.googlecode.com/svn/trunk/pyguide.html?showone=Imports_formatting#Imports_formatting).

i.e. That stdlib comes first, then 3rd party, then local packages, and that
each group is indivudually alphabetized.

It will not check anything else about the imports. Merely that they are grouped
and ordered correctly.

Warnings
--------

This package adds 3 new flake8 warnings

* ``I100``: Your import statements are in the wrong order
* ``I101``: The names in your from import are in the wrong order.
* ``I102``: The import statement is in the wrong group.

Configuration
-------------

You will want to set the `application-import-names` option to a comma separated
list of names that should be considered local to your application. These will
be used to help categorise your import statements into the correct groups.

Limitations
-----------

Currently these checks are limited to module scope imports only. Conditional 
imports in module scope will also be ignored. The classification of an import
as being non-stdlib of some kind depends on that package actually being
installed.
