.. title: Sampling & Aliasing: Square Example
.. slug: sampling-and-aliasing-with-overtones
.. date: 2020-04-28 16:16:05 UTC
.. tags:
.. category: dsp:sampling-quantization
.. link:
.. description:
.. has_math: true
.. type: text
.. priority: 6



For the following example, a sawtooth with 20 partials is used without band limitation.
Since the builtin Web Audio oscillator is band-limited, a simple additive synth
is used in this case.
At a pitch of about :math:`2000 Hz`, the aliases become audible.
For certain fundamental frequencies, all aliases will be located at
actual multiples of the fundamental, resulting in a correct synthesis
despite aliasing.
In most cases, the mirrored partials are inharmonic and distort the signal
and for higher fundamental frequencies the pitch is fully dissolved.

.. raw:: html
   :file: ../dsp/webaudio/aliasing-square.html

-----

Band Limited Generators
=======================

In order to avoid the aliasing, band-limited signal generators are provided in most audio programming languages and environments.
