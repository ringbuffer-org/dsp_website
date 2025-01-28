.. title: Signal Types
.. slug: signal_types
.. date: 2025-01-13 12:00:00 UTC
.. tags:
.. category: dsp:signals-and-systems
.. link:
.. description:
.. has_math: true
.. type: text
.. priority: 2



Signal Types
============

Signals in music and audio DSP can be categorized based on their properties.
The list of categories below is not exhaustive but contains the most frequent
types of sinals.


-------


Continuous vs Discrete
----------------------

All physical signals we can observe in the *real world* - like sound - are time continuous. 
That means a value can be observed for any arbitrary point in time $t$:

$$x(t), ~ t \\in \\mathbb{R}$$

In digital signal processing, signals are time-discrete. 
For these signals, values only exist at the given sampling points $n$:

$$x[n], ~ n \\in \\mathbb{Z} $$


The conversion between continuous and time-discrete signals - sampling - will be treated later in the DSP module.




------

Stochastic Signals 
------------------

Stochastic - or random - signals are those signals whose instantaneous value (the value of the signal at a given point in time) can not be predicted.
They do not have a fundamental frequency or pitch.
Such random signals can, however, be modeled through stochastic processes. 
This means a specific behavior and porperties can be expected - the frequency content and value range.

Some examples for stochastic signals:

- Noise (white, pink, brown)
- Breath/Noise in wind instruments
- Waterfall

-----

White Noise Example:
 
.. raw:: html
   :file: ../dsp/jupyter/signal_properties_noise.html


------

Deterministic Signals
---------------------

A deterministic signal is fully predictable and can thus be expressed in a mathematical function.
For such signals the instantaneous value can be calculated for any point in time.

Typical deterministic signals are:

- periodic signals
- constant signals (aka DC)

------

Periodic Signals
----------------

Periodic signals are the most common type of deterministic signal.
All periodic signals have a fundamental frequency - $f_0$ - the rate of repetition. 
The period $T$ of a periodic signal is the inverse of the frequency:

$$ T = \\frac{1}{f_0}$$

Often, the angular frequency $\\omega$ is used:

$$ \\omega = 2 \\pi f_0 = \\frac{2 \\pi}{T}$$


For musical instruments and speech, the fundamental frequency is in the range of our hearing.
It results in pitch, the perceptual concept related to fundamental frequency. 

Some examples for periodic signals:

- sine wave
- square wave
- saw tooth


-----


Sine Wave
~~~~~~~~~

For many applications in science and engineering, 
including DSP,  the sine wave (or the cosine) is the most important basic function.


$$ x(t) = a \\sin \\left( 2 \\pi f t \\right) $$

.. raw:: html
   :file: ../dsp/jupyter/signal_properties_sine.html

The sine wave is fully described by its frequency $f$ and amplitude $a$.
The argument of the sine function is the (instantaneous) phase.
In many applications, the relation between phase $\\varphi$ and angular frequency $\\omega$
is of importance. They have the same fundamental relationship as speed and accelleration.


**Frequency-Phase Relationship**

The frequency is the derivative of the phase:

$$ \\omega(t) =   \\frac{d \\varphi(t)}{ dt}	$$

And the phase is the integral over the frequency:

$$ \\varphi(t) = \\int \\omega(t) d t$$

-----

**Phase Wrapping:**

In signal processing, the phase is often *wrapped*, when visualized.
Since the sine wave is periodic within $2 \\pi$, it only needs input values between
$0$ and $2 \\pi$ (or in the range of $-\\pi ... \\pi$, when shifted).
*Wrapping* the phase, means keeping it within this range - when the phase
exceeds $2 \\pi$, it continues at $0$.

The following plot shows a sine wave with it's wrapped instantaneous phase:

.. raw:: html
   :file: ../dsp/jupyter/properties_sine_phase.html

------

Quasi-Periodic Signals
----------------------

Music and speech consist of a mix of both deterministic and stochastic signal components.
Even pitched instruments and the human voice are never fully predictable.
However, in most cases it is perceptually sufficient to model musical signals as truly periodic.


------

Transients
----------

In audio DSP, transients are short signal segments, characterized by a rapid change of signal properties.
There is no exact definition, but in general they have a length between $ 1 - 100 \\mathrm{ms} $.
Most transients in speech and music signals are part of the attack - the beginning of a sound.
They contain noise and rapidly changing sinusoidal components, like the struck of a guitar string,
the hammer hitting a piano string or the early breath noise in wind and brass instruments.
Transients are very important for recognizing instruments and defining their individual qualities.


Some examples for transients are:

- Handclap
- Snare drum
- Attack segments
- Noise bursts

Audio example for a transient sound - MFB-522 Clap:

.. raw:: html

	<center>
	<audio controls preload="none">
		<source src="/files/dsp/audio/clap_0.wav" type="audio/wav">
	</audio>
	</center>


------


Textures
--------

Sound textures are created by a random sequence of similar events.
Similar to their visual counterpart, they create a repeating surface.

Some examples for textures:

- Rain
- Fire crackling
- Vinyl crackling
- Frying bacon in a pan


Audio Example for a sound texture - grabbing chips:


Example - MFB-522 Clap:

.. raw:: html

	<center>
	<audio controls preload="none">
		<source src="/files/dsp/audio/chips.wav" type="audio/wav">
	</audio>
	</center>



-----

Signal Segments
===============


In audio and music DSP, signals are often segmented into units that have certain characteristics.
One of the most common envelopes, already featured in early synthesizers
and in prominent examples as the MiniMoog, is the ADSR envelope (Hiyoshi, 1979).
It is comprised of four segments:

- Attack
- Decay
- Sustain
- Release

The attack is the early part of the a sound, before the actual oscillation is established.


In synthesizers, attack time, decay time and release time can usually be controlled by the user via
dials or sliders, whereas the sustain time depends on the duration a key is pressed
and the sustain level may depend on the stroke velocity. Depending on the settings,
the ADSR model can generate amplitude and timbral envelopes for slowly evolving sounds
like strings or sounds with sharp attacks and release:

.. raw:: html
   :file: ../Computer_Music_Basics/webaudio/adsr.html


|

When used in synthesizers, this envelope can be used to control the overall level
or the timbre - for example through the cutoff frequency of a filter or by means
of partial amplitudes.

-----

References
----------

.. publication_list:: bibtex/envelopes.bib
	   :style: unsrt
