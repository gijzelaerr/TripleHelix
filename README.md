# TripleHelix


## Introduction

Tripe Helix is a community driven semi-supervised sound and music generator.
This document describes the basic concepts of the project. It is a early draft
and everything written down is just a collection of idea's and is probably
going to change a lot in the future.

The goal is to create an online participation platform where user supplied data
is used for generating music. User supplied data can be opinions on generated
sounds or compositions, or examples of compositions which will be used by the
learning algorithms.

Since the uprising of computers many creative people have seen the huge
potential computers have to augment creative processes and expression.
Constructing algorithms that generate music have been partially successful.
We believe that collecting and analysing user supplied opinions and modelling
this to generate music has a great entertaining potential, both for the users
and developers. 

To do any kind of automated generation we need to have some model. This can be
for example a set of expert rules, or a set of labelled examples. Making expert
rules is a complex and often boring task. It would be much easier and much more
fun to gather user feedback and generate implicit expert rules from this data.


## Basic Components

The overall design of Triple Helix can be cut down in multiple sub projects,
which can be developed but also used independently. 


### Sound design

This is the most basic step, and is the easiest to get started with.

The most atomic part of the system will be an sound generating module, an
instrument. Generating sound is a well understood problem and there exist many
open source or free to use virtual instruments. This sub-project will be based
on these publicly availably instruments, and will focus on optimizing the
parameters of these instruments.

These parameters can be encoded into string and could be used in for example
a genetic algorithm to combine these strings into new strings. User feedback
like a score can be used to generate new strings of parameters for these
instruments.


#### Implementation

The sort of de facto standard for interfacing between a virtual instrument and a 
host is the VST protocol developed by Steinberg. It is a shared library based
approach which is supported by most digital audio workstation software.

There are many free VST plugins available which we can use, for example this
list:

http://www.resoundsound.com/25-best-free-vst-au-plugins-pc-mac-2013-part-1/

Mrs Watson is a open source implementation of this the host side of the VST
plugin protocol, which can be used to interact with VST plugins.

https://github.com/teragonaudio/MrsWatson



### Music composition

The composition of music a whole lot more complex and requires much more 
thought. A lot of existing research has been performed, we need to read about
that, find interesting idea's and come up with new ones.

Ideas from text retrieval can be used here, like grammar composition and markov
chains.

#### Implementation

Probably it is best to just generate MIDI for now, which we can feed into a tool
like Mrs Watson. There are various Python libraries available for generating MIDI
with Python:

https://code.google.com/p/python-music-gen/



### Mixing and mastering

Mixing and mastering a music composition is a often underestimated necessarily.
Mixing is the adjusting of volumes and equaliser filters per audio track (
so the combined tracks form a well balanced whole.


### Community participation

This project is only going to work if people want to participate. For that we
need a easy accessible and responsive interface to the software.

#### Implementation

As a start we will do server side rendering of audio. bandwidth and storage
is less and less of a problem, and various online cloud computing services like
soundcloud offer online storage and playback of audio although the applicability
requires more investigation. 

In the future it is an interesting idea to investigate the possibilities to 
generate audio inside the browser, which reduces storage & bandwidth
requirements and potentially greatly enhanced usability and responsiveness
of the user interface:

http://oampo.github.io/Audiolet/
