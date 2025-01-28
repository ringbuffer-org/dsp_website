.. title: Python Setup
.. slug: python-setup
.. date: 2024-12-12 12:00:00
.. tags:
.. category: dsp:intro
.. link:
.. description:
.. type: text
.. has_math: true
.. priority: 2





While experienced users can use their python coding environment as usual,
this page shows the recommended workflow for the DSP section of ringbuffer.org.

-----


Install Python
==============

Some operating systems are shipped with an install of python.
In other cases it may have been intalled previously for other purposes.
The most recent (stable) version of Python is recommended for ths class.
This is Python 3.11 or 3.12. Installers can be found on the official download page:

	https://www.python.org/downloads/

Linux users can use their standard package management system (e.g. apt, pacman, yum).
Installers are provided for Mac and Windows.

Windows
-------

- Download and run the installer: https://www.python.org/downloads/windows/
- Or install from Microsoft store.


Allow runing scripts for future operations in the PowerShell:

.. code-block:: bash

	$ Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

-----

Install pip
===========

Pip is the package installer for Python: https://pip.pypa.io/en/stable/

All dependencies needed for this DSP section can be installed with pip. 
To install pip itself, follow the instructions on the 
pip website: https://pip.pypa.io/en/stable/installation/


Linux users should use their standard package management system (e.g. apt, pacman, yum) to install pip:

.. code-block:: bash

	$ sudo apt install python3-pip


-----

Install venv
============

Python can be used inside virtual environments: https://docs.python.org/3/library/venv.html
A venv is treated like an isolated Python install.
Virtual environments can be activated and deactivated.
When activated, the interpreter will only work with the modules and packages installed specifically
in this venv.
This makes it easier to work on multiple projects with different required packages.


venv can be installed with pip:

.. code-block:: bash

	$ python -m pip install --user virtualenv



Linux users can use their standard package management system (e.g. apt, pacman, yum) to install venv:

.. code-block:: bash

	$ sudo apt install python3-venv



-----

Create and Activate Virtual Environment
=======================================

A virtual environment can be created by calling the venv module from the terminal (or PowerShell in Windows).
Run this command in your main working directory for the DSP class: 

.. code-block:: bash

	$ python -m venv dsp_venv

This creates a directory 'dsp_venv'. 
The virtual environment can be activated by running the activate script inside the venv:

Linux/Mac:

.. code-block:: bash

	$ source dsp_venv/bin/activate



Windows:

.. code-block:: bash

	$ dsp_venv\Scripts\activate



-----

Install Modules
===============

Once the virtual environment has been activated, pip will install modules to that venv.
Make sure to run these commands after activation.


NumPy (https://numpy.org/) is a library for arrays and mathematical functions:

.. code-block:: bash

	$ python -m pip install numpy


SciPy (https://scipy.org/) is a comprehensive open-source software for mathematics, science, and engineering:

.. code-block:: bash

	$ python -m pip install scipy

MatPlotLib (https://matplotlib.org/) is a library for creating static, animated, and interactive visualizations in Python.
It offers a workflow similar to Matlab:

.. code-block:: bash

	$ python -m pip install matplotlib


The libraries and modules installed this way are only available when the venv has been acivated.


-----

Install Spyder 
==============

Spyder (https://www.spyder-ide.org/) is the recommended IDE for the DSP section of ringbuffer.org.
Similar to Matlab, it has a layout that allows the inspection of 
variables and plots.

Inside a venv
-------------

Spyder can be installed inside a virtual environment:

.. code-block:: bash
	
	$ python -m pip install spyder



Instructions for other installation procedures are provided here:
https://docs.spyder-ide.org/current/installation.html











