.. title: Python Blackbox Exercise
.. slug: python_blackbox
.. date: 2025-01-15 12:00:00 UTC
.. tags:
.. category: dsp:signals-and-systems
.. link:
.. description:
.. has_math: true
.. type: text
.. priority: 10


LTIs & Impulse Responses
========================

Impulse responses (IR) can fully describe any LTI system.
This relation can be used to *decipher* unknown systems, or black boxes.
An LTI will respond to an impulse with the impulse response.
We can thus send an impulse to a system, and measure the IR at the output.
In the following exercise, three LTI systems will be analyzed in this way.


-----

Get the Impulse Responses
=========================


1. Activate the DSP venv

   - This ensures all modules are available.

2. Download the module `systems.py` and place it in your python working directory.

   - https://ringbuffer.org/download/ringbuffer_data/DSP/LTI/systems.py


3. Load the module

.. code-block:: python

   import systems
   
- The module has three functions, that can be accessed with the dot-syntax:

.. code-block:: python

   systems.system1()
   systems.system2()
   systems.system3()

   - Each function represents an LTI system with an individual impulse response and takes one single argument.


4. Create in Impulse ``x[n]`` 

   - The impulse needs to be a list of integers or a numpy array (even if it is only one element).
   - The amplitude of the impulse is ``1``.
   

5. Create an impulse response for each of the three systems.


-------


Evaluate the Results 
====================

1. Plot the impulse responses with matplotlib.

2. Describe each system in your own words.
 
