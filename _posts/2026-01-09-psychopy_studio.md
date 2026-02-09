---
layout: single
title:  "PsychoPy Studio: the app we love, reimagined"
date:   2026-01-09 13:34
category: "General Blog"
tags: psychopy, history
author: Jon
---


![PsychoPy Studio splash screen 2026](/assets/images/PsychoPyStudio2026.png){: .img-super-right style="width:75%"}

It's now over 20 years since PsychoPy's humble beginnings as an open-source Python library to help users present high-precision stimuli and collect responses from participants. Since 2009 PsychoPy has provided, in addition to the Python library, an application that included Builder and Coder interfaces for creation of experiments. That application was, itself, written in Python using wxPython to provide widgets that could be used to support Windows, MacOS and Linux whereas similar proprietary packages (like E-Prime, or Presentation) were only available on Windows. 

In essence, while wxPython made possible a lot of what we managed to achieve over the last 15 years, it also has some disadvantages and we have taken the step to rewrite from the ground up with a more modern “web-based” technology stack.

We’re very excited at this point to be releasing the new app, which goes by the name PsychoPy Studio and we hope you’ll enjoy the advantages it brings, which are summarised below.

Note, by the way, that the PsychoPy and PsychoJS libraries are unaffected by this change. While the technologies in the app will be dramatically different, your studies will run exactly as before, subject to the normal continuous improvements.

# Faster load times

We all know that the PsychoPy application has always taken a very long time to launch. You don’t want to shut it down for fear of having to watch another iteration of that splash screen!  

So the first noticeable advantage of the PsychoPy Studio application is that it will load in a flash (well, about 2 seconds). After loading the application will continue performing other tasks, like installing and loading whatever Python libraries you need, which is what PsychoPy spent a long time doing at launch, but the application will be there ready for you while those things carry on in the background.

# Modern interface

You’ll hopefully also quickly notice a more modern look and user-interface features that we can relatively easily provide that would have been very hard in wxPython. It doesn’t look vastly different, because we think there were a lot of good things about the existing interface that we wanted to keep, but we’re hoping you’ll notice a lot of minor improvements to the usability.

# Better cross-version reproducibility, with multiple Python versions

Although PsychoPy has, for many years, supported the rare (possibly unique?) ability to switch itself to an older state so that you could install a newer version of the app but run your study in the version you created it in. We think that’s a very important feature of the software for the sake of reproducibility. 

But that feature always had a limitation that it was stuck with whatever Python interpreter and dependencies had been shipped with the app. If you installed a new version of PsychoPy that shipped with Python 3.10, then you could only switch with _useVersion_ back to PsychoPy versions that supported Python 3.10 (which means at least PsychoPy 2023.2.x).

PsychoPy Studio does not include/need any Python in itself, because it isn’t written using Python. What it does is install 1 or more Python “environments” for each version of PsychoPy you use, supporting all PsychoPy releases from 2022 initially. 

Those different Python environments can be loaded with different sets of plugins, different dependencies and can even be entirely different version of Python itself. And you can have as many environments as you like, for as many versions as you need to support in your lab!

# Better separation, easier installations

The new application is being developed more independently of the library, which is better for development, and reduces installation headaches.

At present PsychoPy has a very large number of dependencies, and it can be hard to know which are needed by the application versus being needed by the library - if you don’t use the application because you prefer to write code in your own development environment, then the number of dependencies you need is very much less. 

In the new system you will either install the Studio application, which will then install whatever Python versions and dependencies it needs automatically as a second step. Or you will install the library simply into your own Python environment. It’s more clear which one you need and the dependencies will reflect your own work.

In particular, this should be a huge bonus for Linux users, where installing the original PsychoPy app was most difficult due to the need to compile wxPython on each different version of the operating system.

# The future - creating studies in Pavlovia and on tablets

There’s another feature that we think is going to be huge in this new development which is that, because the app is basically written as a web page that is then packaged inside an electron app, it could also be rendered as an actual web page. That means you could find yourself, in the future, able to edit web-based experiments directly on Pavlovia. It also means we could support editing on Android or iOS devices, for instance, because the app no longer requires Python and all the dependencies.

# How does all this goodness even work?

A lot of software engineers in the world of user-interface development, in recent years, have been focussed on building web applications. It means that JavaScript is where the most modern user interfaces are being written. To make those work in an application that feels like a local “native” app there are then systems like Electron and Tauri that basically allow you to make websites into applications with access to the things developers expect, like the local filesystem which websites normally don’t get access to, for obvious security reasons. You can see the attraction for the developers - JavaScript has become amazingly powerful and can run on any device that supports web browsers (OK, so your washing machine probably won’t run PsychoPy anytime soon, but pretty much everything else can).

So this is the direction of travel for a huge number of software applications now. Even very substantial applications these days, like the Visual Studio Code editor, are basically web pages running in Electron to turn them into native apps.

So our new app uses the Svelte web development framework, inside an Electron shell. It’s all open-source on GitHub, with an MIT license and anyone that knows JavaScript can contribute to the future of the project.

All in all, we’re very excited, and hope you’ll enjoy this new phase of PsychoPy development.
