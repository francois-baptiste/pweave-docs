
========================
 Pweave example gallery
========================


Basic document: FIR filter design
---------------------------------

This example demonstrates most basic chunk options, output and
capturing figures and it is available in several formats.

.. csv-table:: Example in different formats.
   :header: "Format", "Source", "Pweaved", "HTML", "PDF"
   :widths: 8, 12, 5, 5, 5


   texpygments, :download:`<FIR_design_pygments.texw>`, :download:`open <FIR_design_pygments.tex>` , , :download:`open <FIR_design_pygments.pdf>`
   tex, `<FIR_design_verb.texw>`__ , `open <FIR_design_verb.tex>`__ , , `open <FIR_design_verb.pdf>`__
   texminted, `<FIR_design_minted.texw>`__, `open <FIR_design_minted.tex>`__ , ,`open <FIR_design_minted.pdf>`__
   rst, `<FIR_design.rstw>`__, `open <FIR_design.rst>`__ , `open <FIR_design_rst.html>`__ ,
   script, `<FIR_design.py>`__, , `open <FIR_design.html>`__ , `open <FIR_design.pdf>`__
   pandoc, `<FIR_design.mdw>`__, `open <FIR_design.md>`__ , `open <FIR_design_pandoc.html>`__ ,





Below are the commands used to process the examples from command line.


Latex
=====

Pweave has several options for LaTeX output, here is a demonstation of differences:

Latex with pygments syntax highlighting:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:download:`<FIR_design_pygments.texw>`, `<FIR_design_pygments.tex>`__ , `<FIR_design_pygments.pdf>`__ and with IPython shell `<FIR_design_pygments_ipy.pdf>`__.


.. code:: shell

    Pweave -f texpygments FIR_design_pygments.texw
    pdflatex FIR_design_pygments.tex
    Pweave -s ipython -f texpygments FIR_design_pygments.texw
    cp FIR_design_pygments.tex FIR_design_pygments_ipy.tex
    pdflatex FIR_design_pygments_ipy.tex







.. code:: shell

    Pweave -f texpygments FIR_design_pygments.texw
    pdflatex FIR_design_pygments.tex
    Pweave -s ipython -f texpygments FIR_design_pygments.texw
    cp FIR_design_pygments.tex FIR_design_pygments_ipy.tex
    pdflatex FIR_design_pygments_ipy.tex




Latex with verbatim output:
~~~~~~~~~~~~~~~~~~~~~~~~~~~

`<FIR_design_verb.texw>`__, `<FIR_design_verb.tex>`__ , `<FIR_design_verb.pdf>`__ .


.. code:: shell

    Pweave -f tex FIR_design_verb.texw
    pdflatex FIR_design_verb.tex




Latex with Minted package for syntax highlighting:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`<FIR_design_minted.texw>`__, `<FIR_design_minted.tex>`__ , `<FIR_design_minted.pdf>`__ .


.. code:: shell

    Pweave -f texminted FIR_design_minted.texw
    pdflatex -shell-escape FIR_design_minted.tex




.. note::

  Using pygments directly from Pweave is much faster than
  using Minted separately.

reStructuredText
================

`<FIR_design.rstw>`__, `<FIR_design.rst>`__ , `<FIR_design_rst.html>`__ .


.. code:: shell

    Pweave FIR_design.rstw
    rst2html.py FIR_design.rst FIR_design_rst.html





Published from script
=====================

You can publish documents directly using the `pypublish` command.

`<FIR_design.py>`__, `<FIR_design.html>`__ , `<FIR_design.pdf>`__ .


.. code:: shell

    pypublish FIR_design.py
    pypublish -f pdf FIR_design.py





Markdown
========

Pandoc
~~~~~~

`<FIR_design.mdw>`__, `<FIR_design.md>`__ , `<FIR_design_pandoc.html>`__


.. code:: shell

    Pweave -f pandoc FIR_design.mdw
    pandoc -s --mathjax FIR_design.md -o FIR_design_pandoc.html




Python-markdown
~~~~~~~~~~~~~~~

`md2html` and `pandoc2latex` formats produce output that is identical
to pypublish command.

`<FIR_design.mdw>`__, `<FIR_design.html>`__


.. code:: shell

    Pweave -f md2html FIR_design_noweb.mdw





Splitting code to multiple chunks
---------------------------------

This example shows how to split code between multiple chunks to write
documentation within a class using `complete` chunk option.

`<AR_yw.mdw>`__ , `<AR_yw.html>`__ , `<AR_yw.pdf>`__ .


.. code:: shell

    Pweave -f md2html AR_yw.mdw
    Pweave -f pandoc2latex AR_yw.mdw
    pdflatex AR_yw.tex





Miscellaneous
-------------

Linear regression with Statsmodels: `<linear_regression.py>`__ , `<linear_regression.html>`__


.. code:: shell

    pypublish linear_regression.py






About the gallery
-----------------

This page is an executable document that be run using Pweave using
IPython shell to run all examples using::

  Pweave index.rstw


The latest version of the examples with any required extra files are
available from the `Git <http://github.com/mpastell/pweave/>`__
repository in examples directory.

It was created using:


.. code:: python

    >>> import pweave
    >>> pweave.__version__
    u'0.23.2'
