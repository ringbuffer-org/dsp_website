.. title: Aliasing with a Sine Example
.. slug: sampling-and-aliasing-sine
.. date: 2020-04-28 16:16:05 UTC
.. tags:
.. category: dsp:sampling-quantization
.. link:
.. description:
.. has_math: true
.. type: text
.. priority: 4
.. template: jupyter_default.tmpl


In the following example, a sine wave's frequency can be changed with an upper limit of $100\\ \\mathrm{kHz}$.
Depending on the sample frequency of the system running the browser, this will lead to aliasing, once the
frequency passes the Nyquist frequency:

.. raw:: html
   :file: ../dsp/webaudio/aliasing-sine.html
