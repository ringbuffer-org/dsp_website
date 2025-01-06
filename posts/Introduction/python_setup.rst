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


Virtual Environments
====================

Python can be used inside virtual environments.
A venv is treated like an isolated Python install.
Virtual environments can be activated and deactivated.
When activated, the interpreter will only work with the modules and packages installed specifically
in this venv.
This makes it easier to work on multiple projects with different required packages.



Windows
=======

Install IDE
-----------

- https://www.spyder-ide.org/
- VSC
	- https://marketplace.visualstudio.com/items?itemName=ms-python.python


Install Python
--------------

- Download: https://www.python.org/downloads/windows/
- In PowerShell, run 
	python3 
- install from Microsoft score


Create Virtual Environment
--------------------------

In PowerShell:

	python3 -m venv env



Allow runing scripts

	Set-ExecutionPolicy RemoteSigned -Scope CurrentUser


	cd env

	.\Scripts\activate

Install Spyder in venv
----------------------

https://docs.spyder-ide.org/current/installation.html



Install packages
----------------

numpy should be automatically installed

	python -m pip install -U matplotlib



sndfile not working




LINUX
========

Create Virtual Environment
--------------------------


Install Jupyter
---------------


Install matplotlib
------------------


Install numpy
-------------


Install scipy
-------------


Install control
---------------


Install schemdraw
-----------------


Install soundfile
-----------------


