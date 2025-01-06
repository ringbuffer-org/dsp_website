.. title: Python Basics
.. slug: python-basics
.. date: 2024-12-22 12:00:00
.. tags:
.. category: dsp:intro
.. link:
.. description:
.. type: text
.. has_math: true
.. priority: 3


Basics
======

Python is used as the primary programming language for the DSP section of ringbuffer.org.
Although there are various online resources for learning Python,
this chapter introduces the most important aspects.

For further reading:
`as <https://docs.python.org/3/>`_






Syntax
------

No Termination
~~~~~~~~~~~~~~

Unlike many other languages,
python does not require semicolons to terminate statements:

.. code-block:: python

	a=1
	b=2


Indents 
~~~~~~~

In Python, code indents are a part of the syntax. This is a very important and unique feature of python.
This will become more important when using loops and conditions,
as indatation can have an effect on the outcome of the code.

Code blocks always need to have the same indatation level.
When using wrong indents: 

.. code-block:: python

	a = 1
	b = 2
	 c = 3

the interpreter will give the following error message:


	IndentationError: unexpected indent




Importing Modules
-----------------

In Python, modules can be imported to extend the functionality. 
This is the equivalent to including libraries in other programming languages.
Modules can be imported at any point in a script, before they are needed,
but it is commom to import all modules at the beginning.
After import, functions from a module can be called with the dot syntax:

.. code-block:: python

	import numpy
	# call the rand function from numpy's random module
	numpy.random.rand() 


It is common to import modules with shorter aliases for shorter code.
Standard modules have typical aliases, that are used throughout the community:


.. code-block:: python

	import numpy as np
	# call the rand function from numpy's random module
	np.random.rand() 

If only a specific part of a module is needed, it can be imported exclusively
with an alias to make it lightweight and fast:

.. code-block:: python

	# import only the window part of scipy
	from scipy.signal import windows

	# create a Gaussian with twelve values and sigma = 1
	w = windows.gaussian(12,1)


Data Types
==========

Strings
-------

.. code-block:: python

	s = "I am stringing!"
	s[3]
	

Lists
-----

The list is Python's default, builtin data type to store collections of data.
Lists are ordered, mutable and can combine different data types.
Elements of lists can be accessed with brackets.

.. code-block:: python

	x = [1, 0, 4, 3]
	y = [1, "two", 4]

	print(x[2])
	print(z[1])
	


Arrays
------


.. code-block:: python

	import numpy as np
	a = np.array([1, 0, 3, 4])



Control Structures
==================


Loops
-----

Conditions
----------




Writing Functions
=================

Functions are defined using the def keyword.
Arguments are declared in the parenthesis after the function's name.
Return values are specified by the return keyword. Multiple values can be returned if comma separated. 
Note the indent to mark the function's body.

Since python code is not compiled but interpreted, functions need to be defined before they can be called:

.. code-block:: python

	import numpy as np 

	def pythagoras(a,b):
		c = np.sqrt(pow(a,2) + pow(b,2))
		return c

	pythagoras(4, 5)
	

Namespaces
==========

All variables defined at the main level of the program (not in a function or class) are 
stored in the **Global Namespace** as global variables.
All gobal variable can be listed as follows:

.. code-block:: python

	dir()

Every function creates a new namespace while being executed - see the **LEGB rule**.	