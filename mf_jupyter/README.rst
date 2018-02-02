MF Jupyter: Notebook with my suite to easy latex conversion
===========================================================

A one directory package to offer tools to create and convert a notebook
into texfiles for further publications (e.g., article, notes)


Quick Start
-----------

To start a new project in a directory (default is current directory), some files are required to be copied into the project directory. The following command takes care of this step

.. code:: shell

    > mf_jupyter/startnew [directory]


A file called `Untitled.ipynb` will now exist in the project directory. This is a template for a notebook that can be edited as usual.

.. code:: shell

   > jupyter notebook

Once the document is ready, compilation can be done through a simple `make` command, as for example

.. code:: shell

   > SOURCE=Untitled make tufte pdf

Where the `SOURCE` variable is the name of the notebook file and `tufte` is the
template name.


Notebook content and meta data
------------------------------

The furnished template contains a few blocks as example. There are only a few options that are used for converting a notebook. These options are always set through the `metadata` that one can access through the toolbar on each cell. If the toolbar is not visible, use the menu `View > Cell Toolbar > Edit Metadata`.

Recognized metadata keywords
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* `hide`: set to `true` will tell the converter to skip the cell
* `abstract`: set to indicate to the converter that this cell contains the abstract block content.  (`\begin{abstract} ... \end{abstract}`)

.. note::
 
   More keywords will be soon available. 

Python tools
------------

To simplify the interface between python notebook and Latex, `mf_jupyter` provides some tools, such as making captions for figures with labels and the pdf assocaited export. But also some other neat tools. Below is a list of functions (use the python `help` to know more)

* `add_input_toggle`: add a button in the notebook toolbar to hide codes and only keep text and outputs/figures visible. 
* `add_citation_button`: add a button in the notebook toolbar to generate bibtex reference from bibcode.
* `Matrix`: creates a Latex matrix text that can be used as markdown and in latex.
* `LatexFigure`: generate a caption (with label) to go with a figure. This will also save the figure to a file (pdf by default) to be included as floating figure in the latex file
* `LatexSubfigures`: takes a list of python figures to create a single floating figure in latex with optional captions per sub-figure.
* `LatexNumberFormatter`: formats numbers into scientific notations using Latex representation.
* `Table`: Makes a table into a latex table format.
  

Avaiblable templates
--------------------

All templates are usable with make using their name, for example `make mnras`.

Specific
~~~~~~~~
* `dpac`: Gaia DPAC technical note template
* `tufte`: Tufte handsout conversion

Journals
~~~~~~~~
* `apj`: convert into ApJ format
* `mnras`: convert into MNRAS format
