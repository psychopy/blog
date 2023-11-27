---
layout: single
title:  "Contributor story: Hiroyuki Sogo"
date:   2023-11-22 15:38:41 +0100
category: "User stories"
author: Hiroyuki
author_profile: false

---

## How did you start using PsychoPy?

When I was a postdoc, I had to use the Eyelink II eye tracker with Matlab/PsychToolbox on a Windows PC. At that time, EyelinkToolbox was available to control Eyelink II from Matlab; however, it had some problems on Windows. So, I looked for another way and found that a sample code with pylink worked fine on Windows. From then on, I started to be interested in Python. A few years later, I got a teaching position at a Japanese university and chose Python as the language for teaching programming. After trying several development environments and libraries, I selected PsychoPy for its ease of building experiments on the Builder interface. I don’t remember when, but I think it was around 2011.

## What are your contributions to PsychoPy?

Soon after using the Builder for teaching, I faced problems with Japanese characters. Although the Builder could draw Japanese characters as visual stimuli, it crashed if the path to the experiment files included Japanese characters (more generally, multibyte characters). I told students not to use Japanese characters as folder and file names, but that seemed to be an “unreasonable” requirement for some Japanese students. Even worse, Japanese characters in several audio device names also caused crashes, which could not be avoided without hardware change. To solve the problems, I started to read the Builder source codes and commit fixes to the PsychoPy repository. These problems have been solved in recent versions of PsychoPy.

In 2014, the project started to make the Builder UI multilingual. I participated in testing multilingual functions and simultaneously translating the UI into Japanese. Since that time, I have continued to update Japanese translations when new features are added to the Builder or messages in the UI are modified.

In addition, I have been publishing tutorials on Builder on my website since 2014. This led to an offer from a publisher to write two books, one is about programming PsychoPy and the other is about online experiments with the Builder and Pavlovia. I also participated in the translation team for the official PsychoPy book (“Building Experiments in PsychoPy”).

I’m not a good programmer at all, and most of the bugs I fixed were easy to fix; however, they would have been difficult to find for users who didn’t use the multibyte characters environment. Even the best programmers will not be able to find all the bugs under various conditions. So, I hope that people with various backgrounds will contribute to the development of PsychoPy.

## What do you like about PsychoPy?

Active development over the years. It has been more than 10 years since I started using PsychoPy. Many tools and libraries I used have disappeared because they could not keep up with the changing PC environment. Nevertheless, I can still use PsychoPy in much the same way as when I first learned it. 

There have been several challenges over the last decade, I guess, but the one that was the most impressive for me was the transition from Python 2 to 3. Because the syntax of Python3 is not fully compatible with that of Python2, extensive code rewriting was required to run PsychoPy on Python3. It was truly commendable that the core development team and contributors made it through. Hopefully, PsychoPy will continue to be updated in the future — though, to be frank, it’s a burden for me to update my Builder tutorial if updates to PsychoPy occur too often!