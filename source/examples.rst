

.. index:: reST example
.. _rst-example:

reST example
-------------




Here is a simple example of a Pweave file (`ma.Pnw <_static/ma.Pnw>`_) that uses reST as the documentation format. The file demonstrates basic usage of Pweave and how it can easily be used to add dynamic figures and tables.

.. literalinclude:: ma.Pnw

The file was processed with Pweave using:

::

  Pweave -f sphinx --figure-directory=_static ma.Pnw

And as result we get the reST document `ma.rst <_static/ma.rst>`_ (shown below) which uses the Sphinx markup.  *If you want to get pure reST that can be processed with e.g. rst2html document you need to call Pweave with '-f rst' option.*

.. literalinclude:: ma.rst

.. index:: Sphinx example

.. _sphinx-example:

Output of the example in Sphinx
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The produced rst file be included in a Sphinx document, like this website using ".. include:: ma.rst". Here is what it looks like:

.. include:: ma.rst
