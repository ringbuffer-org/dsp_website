.. title: Aliasing with Overtones
.. slug: aliasing_overtones
.. date: 2020-04-28 16:16:05 UTC
.. tags:
.. category: dsp:sampling-quantization
.. link:
.. description:
.. has_math: true
.. type: text
.. priority: 5


The aliasing effect occurs much earlier and stronger, when an input signal with harmonics is used.
The harmonics fall beyond the Nyquist freuqncy, if the fundamental frequency is still well below.
Unlike harmonic distortions, which add spectral components at integer multiples of the fundamental frequency,
aliasing creates a pattern of non-harmonic partials:


.. raw:: html
   :file: ../dsp/webaudio/aliasing_overtones.html
 