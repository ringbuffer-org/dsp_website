.. title: Classes in Python
.. slug: python-classes
.. date: 2024-12-22 12:00:00
.. tags:
.. category: dsp:intro
.. link:
.. description:
.. type: text
.. has_math: true
.. priority: 5


Defining a Class
================

Python is by nature an object-oriented programming language.
A lot of Python's functionality is thus organized in classes and objects and
working with classes is the standard way for most Python projects


A class is defiuned as follows:

.. code-block:: python

    class FirstClass:
        
        # Contructor, always taking the argument self + additional arguments
        # Is called on class instantiation
        
        def __init__(self, a, b):
            self.a = a
            self.b = b
        
        # Methods are defined just like regular functions
        def sum(self):
            print(self.a + self.b)
        
        def diff(self):
            print(self.a - self.b)    

-----

Instances
=========

Once a class definition has been evaluated, instances can be created and methods 
can be called.

 .. code-block:: python
       
    # Create an instance of FirstClass and assigns it to the variable l:
    l = FirstClass(0, 10)

    l.sum() 
    l.diff()

    # No getters and setters needed:
    l.a = 100
    l.sum() 
    l.diff()

Output:

.. code-block:: python

    10
    -10
    110
    90  

-----

Inheritance
===========

The following example shows how the SecondClass inherits all mehods and variables from 
the FirstClass. An additional method is implemented in the child class:


.. code-block:: python

    class SecondClass(FirstClass):   
        
        def prod(self):
            print(self.a * self.b) 
                
    m = SecondClass(3, 3)
    m.prod()
