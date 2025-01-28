.. title: Python and Numpy
.. slug: python-numpy
.. date: 2025-01-09 17:00:00
.. author: Noel Alben
.. tags:
.. category: dsp:intro
.. link:
.. description:
.. type: text
.. has_math: true
.. priority: 8



Things to keep in mind as a beginner programmer
-----------------------------------------------

-  Aim to write re-usable code
-  Write clean and documented code
-  Write code with no bugs
-  make it work, then make it right, then make it fast

We will be programming in Python for this course, this is a rapid fire
primer to get started working in Python. Here is a list of resources to
get started and understand the where python exists within the larger
scope of programming languages and programming.

Python Origin - https://www.geeksforgeeks.org/history-of-python/

Data Types - https://www.w3schools.com/python/python_datatypes.asp

OOP: https://www.geeksforgeeks.org/python-oops-concepts/

Libraries in Python: https://www.geeksforgeeks.org/libraries-in-python/

Numpy Tutorial:
https://www.w3schools.com/python/numpy/numpy_array_search.asp

Variable Naming:
https://www.w3schools.com/python/python_variables_names.asp

Python is an interpreted language, all you need to know about within the
scope of this course is that - “interpreted languages are easier to test
and modify changes in code quickly, but may run more slower compared to
compiled languages”

More on that:
https://www.geeksforgeeks.org/difference-between-compiled-and-interpreted-language/

-----

Writing Code For This Class
---------------------------

For your assignments and exercises you will be asked to write and submit
Python scripts. You will be evaluated on how well the code runs and
correctness, but a good percentage of your grade is dedicated to clean
coding practices and proper documentation.

To ensure a smooth experience, we want you to work in virtual
environments. We walk you through setting up a virtual environment here:

https://ringbuffer.org/dsp/Introduction/python-setup/

More info on environments and how they work can be found here:
`https://csguide.cs.princeton.edu/software/virtualenv#:~:text=A Python
virtual
environment <https://csguide.cs.princeton.edu/software/virtualenv#:~:text=A%20Python%20virtual%20environment%20>`__


-----


Python Tutorial
~~~~~~~~~~~~~~~

Activate your virtual environments

MAC/OS/ Linux

.. code:: bash

    source dsp_venv/bin/activate

Windows

.. code:: bash

   dsp_venv\Scripts\activate

There are many ways you can edit, run and read python code on your
systems. We will work with VS Code and Spyder as the Integrated
Development Environments to edit, navigate and debug our source code.

You can open VS code with your terminal, follow the steps here:
https://www.geeksforgeeks.org/how-to-open-vs-code-using-terminal/


-----


Coding
~~~~~~

.. code:: python

   import numpy as np

   # Create an array of integers
   arr = np.array([1, 2, 3], dtype=np.int32)

   # Create an array of floats
   arr = np.array([1.2, 2.3, 3.4], dtype=np.float64)

   # Convert an array to a different dtype
   arr = arr.astype(np.int64)

   # Creating an array of zeros
   arrZeros = np.zeros(5)

   #Creating an Array of Ones

   arrOnes = np.ones(5)

   # Creating mULTIDIMENSIONAL ARRAYS

   arrOnesMulti = np.ones((5,2)) #5 rows 2 columns

   # Creating an array with a ceratin range 

   rangeArray = np.arange(0, 10, 2) # Start 0 go to 10 jump in 2s

   # Random array

   randomArray = np.random.randint(10, size=(5, 3))

   # Random array of floats (between 0 & 1)
   np.random.random((5, 3))

   # Set random seed to 0
   np.random.seed(0)
   # Make 'random' numbers
   np.random.randint(10, size=(5, 3))
   # Pseudo Random

   # Slicing and Indexing - special array creation
   x = np.arange(10)
   print(x[2:4])

   xLin = np.linspace(0, 100, 5) # Range, and how many in that range
   print(xLin)

   # Last element of the array

   print(x[-1])

   print(x[0:8:2]) # In steps 

   #Backwards Slice 
   print(x[4:2:-1])
   print(x[::-1])

   x = np.arange(5)
   y = np.ones(5)
   print(x+2*y)

   # Sorting with Numpy

   x = np.random.randn(5)
   print(x)
   x.sort()
   print(x)

   # Sorting and getting the rearranged indices 

   x = np.random.randn(5)
   print(x)
   ind = np.argsort(x)
   print(ind)
   print(x[ind])

   # Iterating

   arr = np.array([[1, 2, 3], [4, 5, 6]])

   for x in arr:
     for y in x:
       print(y)

   # Conditionals and search

   arr = np.array([1, 2, 3, 4, 5, 4, 4])

   x = np.where(arr == 4)
