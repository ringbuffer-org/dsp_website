.. title: Plotting with Matplotlib
.. slug: python-plotting
.. date: 2024-12-22 12:00:00
.. tags:
.. category: dsp:intro
.. link:
.. description:
.. type: text
.. has_math: true
.. priority: 5


Matplotlib's is a library for plotting in Python in a similar way it is handeled in Matlab. 
It is usually used with pyplot - an interface for using matplotlib.
Other notable plotting libraries are Seaborn, Plotly and an API inside pandas.

The following example shows the minimum effort way of plotting with Matplotlib.
After importing pyplot and numpy, a parabola ``y`` is calculated from a set of values ``x``.
The ``.plot()`` function takes two arguments and plots them as  abcissa  and ordinate, respectively:


.. code-block:: python

    from matplotlib import pyplot as plt
    import numpy as np

    # input values
    x = np.linspace(-1,1,100)
    # calculate parabola    
    y = np.pow(x,2)

    # plot
    plt.plot(x,y)


Axis Labels & Legends
=====================

.. code-block:: python

    from matplotlib import pyplot as plt
    import numpy as np

    # input values
    x = np.linspace(0,4*np.pi,100)
    y1 = np.sin(x)
    y2 = np.cos(x)

    # plot
    plt.plot(x,y1, label="sine")
    plt.plot(x,y2, label="cosine")

    plt.legend(loc="lower left")

    plt.xlabel("x")
    plt.ylabel("y")



.. figure:: /images/dsp/python_plot_legend.png
	:figwidth: 100%
	:width: 60%
	:align: center    




Exporting Plots
===============


Print to Graphic File
---------------------




Export as PGF/Tikz
------------------


.. code-block:: python

    import matplotlib
    import matplotlib.pyplot as plt
 
    matplotlib.rcParams.update({
        "pgf.texsystem": "pdflatex",
        'font.family': 'serif'
    })

    plt.plot([1,2,3])

    plt.savefig('myfig.pgf')

If no LaTex system is installed, the pfg file is created but an error is thrown.
Backends are 

    - 'xelatex'
    - 'lualatex'
    - 'pdflatex'

TexLive is recommended (big package):

    https://www.tug.org/texlive/windows.html

    $ sudo apt install texlive-full
