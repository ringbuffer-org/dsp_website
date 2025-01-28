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


 

Python is used as the primary programming language for the DSP section of ringbuffer.org.
There are countless nigh-quality online resources for learning Python and this chapter does not
intend to give a full introduction.
Rather, it is a primer that covers some of the relevant aspects to make it easier to get started.

Additional resources might be necessary. 
The official Python documentation is recommended in this case:

	- https://docs.python.org/3/

Another resource for detailled examples can be found here:

	- https://www.w3schools.com/python/


------


Syntax
======

No Termination
--------------

Unlike many other languages,
python does not require semicolons to terminate statements:

.. code-block:: python

	a=1
	b=2

Termination can be necessary in some cases to suppress output from functions.

Indents 
-------

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


------


Importing Modules
=================

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

------


Data Types
==========

Strings
-------

.. code-block:: python

	s = "I am stringing!"

	# single characters can be accessed with brackets
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

Numpy arrays allow only the same datatype. 
They offer more operations than simple lists and can be created with different methods:

.. code-block:: python

	import numpy as np
	a = np.array([4, 1, 0, 3])

	print(a.argmin())
	
	x = np.linspace(0,1,4)
	print(x)


.. code-block:: python


	2
	[0.         0.33333333 0.66666667 1.        ]


.. admonition:: Exercise

	Find the mean value of x with numpy. 		


------


Control Structures
==================


While Loop
----------

.. code-block:: python

	i = 1

	while i < 1:
		
		print(i)
		i+=1	


For Loop
--------

For loops in Python iterate over a list or other sequences:

.. code-block:: python

	for i in range(0,9):

		print(i)

Note that the range function creates a list of integers, counting from 0 to 9.
This example is a more explicit loop over a list:

.. code-block:: python

	x = [0,2,4,9]

	for e in x:
		
		print(e)


Conditional Statements
----------------------


.. code-block:: python

	a=1
	b=2

		
	if a>b:
		print('Foo')
	else:
		print('Bar')    


elif is an additional conditional statement that is evaluated if the previous if is false:

.. code-block:: python


	a=2
	b=2

		
	if a>b:
		print('Foo')
	elif a<b:
		print('Bar')    

.. admonition:: Exercise

	Add one character to the above example to let it print "Bar".


------


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
	
------

Namespaces
==========

All variables defined at the main level of the program (not in a function or class) are 
stored in the **Global Namespace** as global variables.
All gobal variable can be inspected in an IDE like Spyder and `listed as follows:

.. code-block:: python

	dir()

Every function creates a new namespace while being executed - see the **LEGB rule** (Local, Enclosing, Global, and Built-in).	