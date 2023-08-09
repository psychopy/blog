---
layout: single
title:  "The origins of PsychoPy"
date:   2023-07-31 15:25:41 +0100
category: "PsychoPy"
tags: psychopy, history
author: Jon
---

The seeds of PsychoPy were planted in early 2000s when Jon Peirce was a visual neuroscience postdoc at NYU. Jon had been using [Matlab](https://www.mathworks.com/products/matlab.html) for his PhD and postdoc work but he was never really a programmer. He was just a psych/neuroscientist using code for his needs.

Although Jon had no computer science, like many scientists, he became reasonably fluent in programming. He was using Matlab and Psychophysics Toolbox. In those days, however, PsychToolbox couldn't do all the things it can now - stimuli had to be precomputed as movies, or you had to use sneaky tricks like "lookup table animation" (now long since forgotten).

## The beginnings of PsychoPy

Around this time, there was a lot of talk about "hardware accelerated graphics" and Jon went through the tutorials for using OpenGL. He saw that this would allow a pretty great way to create stimuli that could be generated on the fly, and that meant not having to pre-computer movies in order to generate, say, a drifting Gabor. Jon was pretty excited that this was the way to go for stimulus rendering and he also found that in Python he could execute these OpenGL calls directly in his scripts. 

Now, in 2002, Python was not well-known and in many ways was in its infancy (bear in mind that `numpy` wasn't created until 2005!) but Jon was pretty excited by this and set about creating his first stimuli that combined textures (gratings and gaussian blobs) in useful ways to create stimuli like Gabors. It was all done relatively efficiently on the graphics card with really minimal easy-to-use scripts. 

That was the beginning of PsychoPy, which was uploaded to sourceforge.net as `psychpy` in March 2002 (the "o" got added later but sourceforge didn't allow names to be changed after registration).

In 2003 Jon moved to Nottingham University as a Lecturer (Asst Prof) and began using PsychoPy for his own studies from then on.

## Gradual growth

In the early years PsychoPy had a few users, a web page, a Google Group, but Jon didn't really provide much in the way of formal support. PsychoPy was for his lab and he made it available, but if it didn't work for you on your system that was your issue! Well, that's not quite true. Jon discovered that the power of Python meant that he could add things with relatively little effort and so he often spent his evenings and weekends adding features that users requested. He added more stimuli, and the Coder interface, and built the dependencies into an app so it could be installed more easily. That set of features led to the first manuscript about PsychoPy in 2007 (Peirce, 2007).

## Builder interface

Jon was teaching psychology undergraduates to use E-Prime in their practical classes at Nottingham. That wasn't suitable for psychophysics stimuli (it couldn't create the sort of stimuli that vision scientists need) but it was the only software at the time that had a simple enough graphical user interface for undergraduates (and other non-programmers) to create their own studies. Some discussions with André Gouws at the University of York, encouraged Jon to think about what an ideal graphical interface would look like for PsychoPy and to work out the mechanics of what that might do. This was the beginning of creating the Builder interface. It was a lot of work, mostly in evenings and weekends, but by 2009 this was available with a range of simple stimuli and flow controls, as well as the option to add code snippets. It meant that people could use PsychoPy who didn't have any programming experience and it quickly gained traction as a teaching tool. The inner workings of the Builder interface have changed rather little since that first iteration, although the stimuli, and visuals have improved enormously.

