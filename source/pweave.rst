
=====================
 Using pweave module
=====================

.. currentmodule:: pweave

Pweave can also be used as module from the Python interpreter. This
has some advantages over just using the scripts. First the execution
of the code will be faster because all modules all already
imported. It is also possible to fully
customize the document execution and formatting using the :py:class:`Pweb` class.

pweave module contains two functions :py:func:`weave` and
:py:func:`tangle` that offer the same functionality as the command
line scripts.

.. note::

  This document was also created with Pweave, have a look at the
  `source <_static/pweave.rstw>`_.


Simple weaving and tangling:
============================

Here's and example of simple weaving and tangling using example
document `ma.mdw <_static/ma.mdw>`_. Notice that pweave prints out the
progress so in case of an error you can tell in which chunk it
occurred.


.. code-block:: python

    import pweave
    # Weave a pandoc document with default options
    pweave.weave('ma.mdw', doctype = "pandoc")


::

    Processing chunk 1 named None from line 22
    Processing chunk 2 named None from line 31
    Processing chunk 3 named None from line 42
    Weaved ma.mdw to ma.md
    




.. code-block:: python

    # Extract the code
    pweave.tangle('ma.mdw')




Pweave function reference
--------------------------

.. autofunction:: pweave.weave

.. autofunction:: pweave.tangle

.. autofunction:: pweave.publish

.. autofunction:: pweave.convert

.. autofunction:: pweave.spin


More options with Pweb Class
============================

Weaving, tangling and pweave options are implemented using
:py:class:`Pweb` class. There is an `example <customizing.html>`_
about customizations and the class reference is below.

Pweb Class
----------

.. autoclass:: pweave.Pweb
   :members:
