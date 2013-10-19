########
Tutorial
########


Simple Script-based Plotting
============================

To make a simple plot with bokeh, just make a small script containing
the following::

    from bokeh.plotting import *
    from numpy import *
    x = linspace(-2*pi, 2*pi, 100)
    y = cos(x)
    output_file("cos.html")
    line(x, y, color="red")
    scatter(x, y, marker="square", color="blue")
    show()

You can find this file in `examples/tutorial1.py` in the Bokeh source tree,
or `on github <https://github.com/ContinuumIO/Bokeh/blob/master/tutorial/tutorial1.py>`_.

Let's look at each line in detail.
::

    from bokeh.plotting import *

This imports a variety of plotting functions from the `plotting` subpackage.
(This is not the only way to construct bokeh plots, but it will be the most
familiar for those coming from packages like Matplotlib or gnuplot.)
::

    from numpy import *
    x = linspace(-2*pi, 2*pi, 100)
    y = cos(x)

These lines create two Numpy arrays.  Bokeh does not require the use of
Numpy arrays - two Python lists of numbers would have worked just as well -
but it does have special knowledge and handling of Numpy and Pandas data
structures.
::

    output_file("cos.html")

This tells bokeh to create an HTML file for us.  This file will contain
all the plots we create, as well as the source for BokehJS and its 
Javascript dependencies.  Consequently, it can be quite large - over
a megabyte or more.  It is possible to configure the details of HTML
file generation, so that relative links are used.  Please consult
the :ref:`output_file` documentation.

The next two lines create a line plot and a scatter plot:
::

    line(x, y, color="red")
    scatter(x, y, marker="square", color="blue")

Finally, there is a command to save the plot and display it in our
default web browser::

    show()

This should produce the plot shown below:

.. image:: images/tutorial1.png



Using IPython Notebook
----------------------


Plot Server and Embedding
-------------------------



Customization
-------------

