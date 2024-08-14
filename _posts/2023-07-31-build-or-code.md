---
layout: single
title:  "To build, or not to build, that is the question"
date:   2024-08-14 15:25:41 +0100
categories: PsychoPy
tags: builder coder psychopy
author: Jon
---


This is a somewhat heated debate - we have scientists arguing passionately[^academics] for both sides; that users must always write their own code by hand, or that people should use a graphical user interface to write the code for them. Luckily PsychoPy provides both interfaces, so both groups can be happy.

It is true that PsychoPy Builder was _originally_ designed as a tool to support non-programmers and, when creating that interface, Jon was still expecting to use hand-written code for his own studies. That changed. As Builder became more capable, the number of studies that it could cope with grew. The number of studies that warranted the additional hassle[^hassle] of writing code by hand shrank. It's true that there are likely to be some places that code is necessary or useful - a pure no-code solution could not achieve the level of flexibility that code can, or to do so it would have to be just as complex as writing the code yourself - but by providing an interface that accomplishes all the common tasks by graphical components, and then allows extensions with code where needed, we might get the best of both worlds. By around 2015, all of Jon’s own studies were being created in PsychoPy Builder, with Code Components added, where needed, to achieve the sort of non-standard features that aren’t possible in “no-code” solutions.

Actually, on reflection, the notion of the debate from _both_ sides is not quite true on this occasion. On this topic, the argument nearly always comes from those in favor of hand-writing the code. There is, for many, a belief or assumption that the people using the graphical builders are only doing so because they lack the skills or commitment to write their code by hand. Here, we aim to readdress that balance by considering the genuine scientific advantages that might arise from builder-style interfaces. We will also consider some of the common arguments for why scientists should write code by hand and how much merit these arguments have. 

Advantages of a Builder interface
  - An abstraction of your experiment design
  - Best current practice
  - Generalizing to other systems
  - Reusable in the future
  - Fewer bugs
  - Speed of authoring

Common arguments for hand-writing code
  - I just like writing code
  - I like to know what my code is really doing
  - I like my code to be clean, whereas generated code is ugly
  - With code I can get help from ChatGPT


[^academics]: PsychoPy users are mostly academics, after all, and one thing academics do well is hold their viewpoints passionately

[^hassle]: including the initial debugging, the mistakes, the issues that one failed to think about (that would have been handled correctly in the Builder-generated boilerplate code)

## Advantages of a Builder interface

Before considering some of the reported disadvantages of using a graphical interface, let's consider some of the advantages that it may bring, beginning with developing a greater understanding of the representation that a Builder experiment in PsychoPy actually is.

### An abstraction of your experiment design

When you create a study using Builder you specify very precisely the features you want your experiment to have, without necessarily dictating the manner by which that should be achieved. For instance, you specify the exact nature of your stimuli and responses, such as the timing, the spatio-temporal form and the responses you consider valid. Consider this a very precise, detailed Methods section except that it literally contains every part of information needed to run the study, unlike the average Methods section.

As with a Methods section, there may be times where it becomes important to specify exact details of how something was achieved, notably when we use particularly novel methods or when the exact implementation details will have a big impact on results but, in general, specifying what the experimenter aimed to present and when is the appropriate level of detail. If that is the case then you may well choose to use hand-written code for that part of your study, but it doesn't necessitate that you hand-code everything. You may need a very particular stimulus configuration but randomizing your trial order is probably not something that requires exact specification.

With PsychoPy, the underlying file format is basically an XML file with an open specification and you could actually go and edit that description of your experiment manually if you chose to. The Builder interface is really just a way of visualizing and editing those XML files, which are then used by the software to generate Python or JavaScript files.

Specifying an abstract description of your study, rather than its exact implementation details, has several advantages that we will come onto next, notably the fact that the description can be generalized to any other platform for generating experiments and the fact that the current best practice may change, and the fact that 

### Generalizing to other platforms/languages

In time the software we use changes. Our supervisors will crow about how they used to store their code on some archaic computer in a long-obsolete storage device (do you remember floppy drives? tape storage? punch cards?!) and wrote their experimental code on a series of languages that have changed across time (such as Assembly Language, then C, then Visual Basic, Matlab and Python). It won't be long before some new language appears on the scene and supersedes the current options. 

When that transition to a new language occurs, as it surely will, having all the lines of code, written in a language that nobody understands anymore, is a lot less useful than having a very precise description of exactly what the code was written to achieve. When Pelli and Watson wrote their paper on QUEST adaptive staircases they provided a piece of code written in BASIC as the most precise description of the method they could conceive, and if you still have a BASIC compiler it will probably still work. Unfortunately, in 2024, that code is surprisingly unhelpful to many people in trying to understand the algorithm with very little understanding of that language, which in the 1980s had been ubiquitous.

Potentially we could translate line-by-line the code of a study into our new target language, or get AI to make the translation for us. Unfortunately, languages often don't have direct line-by-line translations; language logic and structure can differ as well as individual words.

This has been shown by the fact that PsychoPy Builder can now output a choice of Python or JavaScript file from a single experiment, and it could easily be extended to output other language implementations, where those provide a similar stimulus/response feature set.

With an abstract definition, the author of the final code only needs to understand the language they are writing the code in, not the implementation details of the language it comes from. That makes a Builder experiment more future-proof than a Python script.

The principle that an experiment builder platform can be made language agnostic became particularly noticeable during the global Covid-19 pandemic, when scientists all over the world were suddenly prevented from going into their labs. If they wanted to try and run their studies online instead, rather than wait out the lockdowns with no new data, they needed to switch to using JavaScript in order to run their study. Those users that had written their studies by hand in Python code were faced with the daunting task of having to translate their code line by line or to start from scratch with a new platform (like jsPsych) in order to run their studies. Conversely, those that had created the study in PsychoPy Builder, had an abstraction of the study description already and PsychoPy could use that, relatively painlessly, to switch to generating an almost identical study online. It was a painful time for everyone, but slightly less so for the Builders.

### Reusable in the future

Maybe worrying about preserving your experiment for future computer languages seems too far into the future for the average scientist, but most can relate to going back to a script they have received from a colleague or from "past you". When you write a piece of code, you hopefully understand it, but that doesn't mean that "future you" in a year or two will still understand it. 

Even if you are competent in the language the study was written in, even if it was written by "past you", modern studies typically run to hundreds of lines of code, often written in a hurry with bits bolted on at the last minute, sometimes including clever "tricks" that seemed genius at the time but the meaning of which is now lost in time. A graphical representation, with code snippets to cover the less-standard details, is much easier to understand in the future. Reusability has been improved. 

Many scientists are also somewhat nervous about sharing their code. They have no formal computer training and they fear that peers will laugh at their inefficient code or, worse, find a bug that changes the interpretation of their data. A study written in a graphical interface feels less scary to share. You don't need to be a PsychoPy expert to work roughly what a PsychoPy Builder experiment is doing from its graphical interface. Again, reusability has been improved. 

Using a Builder interface with clear visualization of the key parts of your study is just you being kind to "future you" and to others around you by providing something we all can understand.

### Best current practice

Very few scientists and programmers read the entire manual of a programming language. They maybe look at a few demos of the features they need and hopefully check the sections on things they care particularly about, like "how do I make sure my timing is good?" or "how do I calibrate my monitor?". But very few read the whole manual and really know the best practice for the software.

The software does. It was written by the same team that wrote the underlying library and knows more of the details and limitations. For instance, PsychoPy has a distinction between regular timing and non-slip timing (where the timing will autocorrect for small over-/under-shoots to keep total time exact). Non-slip timing isn't something that most users probably have a good grasp of and use in their scripts but they get it "for free" if they use PsychoPy Builder. 

Furthermore, even the diligent user that read the entire manual when they learned the software probably didn't keep up to date with every change since. Although relatively detailed changelogs are available and, indeed, GitHub allows you to check every line of changed code between versions, nobody has the time to go through this on each release. Users will tend to write code that was optimal at the point when they first learned the language.

The code being generated by PsychoPy Builder can be, and is, updated alongside changes to the underlying library to reflect the current recommendations of the developers.

As an example of this, the main function in PsychoPy to check keyboard responses was originally `event.getKeys`. This function worked reasonably well, especially if it was called repeatedly while no visual stimuli needed updating, but the later `Keyboard` class has considerably better performance and flexibility. Most critically, it checks and time-stamps keypresses in a separate CPU process so that it isn't hampered by stimuli being rendered at the same time. Builder has naturally been using this higher-performance system as the default for years but, we suspect, hand-written code by perfectly competent programmers is still likely to use the lower-performance `event` module, which is still widely found in demos, and is the recommendation of ChatGPT at present.

### Speed of authoring

The most obvious advantage of using a graphical interface is the speed of creating a study. The user doesn't need to spend nearly as much time (or mental resources) thinking through the code and the steps of their study. Whereas creating a relatively "standard" study in some programming languages would take weeks, in the PsychoPy library we're proud to say it might typically take hours for a proficient programmer but in the Builder it can be generated in just a few hours. Indeed the question of whether it ever takes more than a few hours to fully program a study depends almost always on how much additional hand-written code is needed to augment the Builder generated-code in this study.

Being able to create experiments faster, especially by not wasting time on regular repetitive needs like setting up trial ordering and response gathering, is really a fundamental advantage to any laboratory.

Science needs us to be productive and we should be investing our neural resources and time in solving scientific questions rather than fulfilling basic tasks. 

### Fewer bugs

As well as being quicker, experiments created in a graphical interface will tend to have fewer bugs. While writing thousands of lines of code any scientist or programmer is likely to make occasional errors. In hand-written code one slip of the keyboard can have a profound effect on the successful execution of the study, and the effects of the bug may only be apparent very much later. 

Of course, using a graphical interface does not completely insulate us against human error - we can still type values incorrectly into the boxes or configure a stimulus in the flow of the experiment. It also adds a new element of trusting that the code generated by the computer is correct, although, at least with PsychoPy this is something readily available to check. 

Certainly the PsychoPy team are very strong advocates of piloting your study very carefully, checking the timing, the log files and the data files before proceeding with data collection, however you generate your task. 

While we aren't aware of any data around the topic of whether hand-written or Builder-generated code has fewer bugs, we have a strong suspicion it is the latter.

## Common arguments for hand-writing code

Despite these arguments in favor of graphical experiment builders, like that in PsychoPy, a large number of scientists are very resistant to the idea of using such an interface. As one former colleague of mine once explained, "It just feels dirty to use something so easy"!

So let's consider some of the common arguments for hand-writing your own code.

### I like to know exactly what my code is doing

This by far is the most common argument for hand-writing code. We certainly agree that learning to code is really important and having as much understanding of the underlying Python code of your study is a worthwhile endeavor in understanding certain features and limitations of the platform that you use. That is why we wrote PsychoPy to expose the script to you, and why all the source code of the underlying libraries is available, so that the user truly can completely understand the code of their study. (We note that not all graphical interfaces make this possible, or at least easy, and that is a source of some concern).

However, the truth is that a high percentage of users that write their own code do not have as deep a level of understanding as we would consider necessary. Indeed, as mentioned above, even if they have excellent understanding at one point in time, it can be very easy to let your knowledge of the current best-practice slip, and this is something that constantly changes, as libraries improve, as the languages improve and as operating systems change.

So, if you find yourself saying that you like to know exactly what your code is doing, ask yourself whether you really do. When you look at the Builder-generated code are there parts where you aren't clear why PsychoPy takes a seemingly unintuitive step. Is it possible that PsychoPy Builder is taking something into account that your hand-written code does not, that it does something useful you hadn't yet understood? 

Of course, there are going to be some programmers that do have a better grasp of things like Python, OpenGL and computer timing than the PsychoPy development team, and will write better code than the Builder as a result, but we suspect these are relatively few as a percentage. To the reader that is an exceptional programmer that has been offended by this section, we sincerely apologize.

### Code is more flexible than a graphical user interface

Certainly, if a graphical interface could generate all the realm of experiments that can be created in a programming language, that graphical interface would probably be so complex it would be at least as hard to use as the programming language itself. 

For the PsychoPy team, that was never the goal. The aim has always been, as XXX the author of Perl put it, to "make easy things easy and make hard things possible". The best way to achieve that goal is, we believe, a graphical interface to cover the majority of standard tasks, combined with a coding interface that allows you to build whatever level of flexibility on top of that with your own code. 

Nobody ever suggested that scientists would stop writing code at all. PsychoPy provides the opportunity to include Code Components that augment your study and these can be used to include all manner of exciting additions. This is an extremely important part of PsychoPy's design and future-proofing, that the feature set does not stop with just the components that are already built in. 

When we hear that users need to hand-write code in order to gain flexibility, we tend to find that they underestimate what can be achieved with a well-written Code Component. Code Components bring all the flexibility of Python with code that can be injected almost anywhere in your study, to run at initialisation, at the start of each trial, on every screen refresh etc. 

This code can include custom classes that the scientist has written (benefiting from inheritance from PsychoPy's built-in classes) and can even override behaviors of existing code in the study. Due to the powers of the Python language, you could, for instance provide a new method to override the behavior of the `Window.flip()` function, you could insert this new function into your Code Component, or you could import that from another file to be reused in other studies. If you find yourself using this functionality a lot, you could even make your life easier by creating a Custom Component (an under-used feature of PsychoPy) or making it available to others as a plugin. 

There might be a very small number of behavioral studies that really require you to write a script with no Builder-generated code at all - where you really need to break out of the concept of trials entirely, for instance or don't want a stimulus window to appear. For nearly all other cases, allowing Builder to write the bulk of the code and adding your specialist code into the experiment seems closest to that goal of making easy things easy and hard things possible.

### But I like writing my own code

This is another common sentiment. For many users, the problem-solving task of writing the code is a hugely enjoyable and rewarding part of the job. As scientists that have become software authors, we probably feel this more strongly than almost anyone. It was Jon's enjoyment of writing code that led him to spend so much time developing PsychoPy and that led Becca to work for Open Science Tools. We get it. 

Again, in PsychoPy, you can use those Code Components to go the extra mile and create your studies that are richer than than would have been possible without, and you will naturally get to "scratch" that coding "itch" along the way.

### I like my code to be clean, whereas generated code is ugly

We do appreciate this aspect as well. It is true that Builder often has to write more verbose code than you would do manually, because you know your intention before you start writing the code whereas Builder has to prepare for a very general solution and that often needs more code. 

The PsychoPy team have always aimed to make Builder-generated code as readable as possible, with plenty of comments and avoiding more advanced programming "tricks" that only coding aficionados would understand. That said, the greater priority is that the code works to support a wide range of study and that it runs fast, especially while stimuli are being rendered. Those are greater priorities than readability given that the code is primarily meant to be _run_ rather than _read_.

### With code I can get help from ChatGPT

This rise of ChatGPT and other Large Language Models (LLMs) is an interesting development in terms of how to generate code for studies. These are interesting and fun tools. Certainly the LLMs we have used (ChatGPT and Google's Gemini) have clearly been trained on PsychoPy code and are capable of generating PsychoPy code as a result. They could be used in a variety of ways, all the way from "how can I make these lines more efficient" to "create me a study that does...".

Most interestingly, it seems the same PsychoPy users advocating for writing code "so that you know what it's doing" would prefer to use AI than use Builder. To be clear, you know _much less_ what AI is doing than what Builder does. Builder has been written to generate the same code every time, following known rules by the creators of the software. While AI-generated code may look sensible and provide useful ideas at times, it has several downsides.

First, to provide enough detail to your AI tool for it to know exactly what your experimental script should look like, is to provide the same set of details that your Builder experiment requests from you in creating your study. If you don't give all of those details, if you don't remember all the parameters required to define your stimulus for instance, then your study will be under-specified. ChatGPT won't tell you that it needs more information - it will just generate something that the researcher did not want.

Second, akin to the issue that people hand-writing their code have a strong potential to be out of date, that is also very much the case for LLMs. The material on which LLMs are based will tend to be based on what is found online, through GitHub for instance. Older code examples online will tend to remain, and often even have more links pointing to them, so the LLM will have a tendency to be outdated. Again, Builder is written by the team that creates the PsychoPy code, and generates code according to the current best practice.

Third, the LLM does not have any understanding of the _meaning_ of the code it writes or how the code actually works. The way that LLMs work, put very simply, is to regurgitate and combine phrases that it has encountered previously and generates the plausible phrases responses to a particular prompt.  Builder-generated code ultimately comes from the same developers that know _why_ this code is written this way.

Fourth, the LLM does not create reproducible outputs. Its responses are probabilistic and it generates a different output each time you ask a question. Builder is deterministic, following a fixed set of explicit rules, that you can openly investigate in the source code, and it will always generate the same script for the same code for a given study (for a given version of the software, which can be forced during the compilation of the script).

Lastly, when there are gaps in an LLM's "knowledge" it never alerts you that it doesn't "know" the answer. It just makes an answer up. When you ask ChatGPT to provide references on a discussion, it will often simply make up plausible-sounding papers, that don't actually exist. With code, ChatGPT will assert that functions and arguments exist that simply don't! OK, those errors you may work out soon enough because the code will simply not run. What about when code looks correct to a novice user, and runs without error, but fails to achieve the aims of the researcher or makes more subtle mistakes by not "understanding" the underlying meaning of the phrases it puts together.

## Ultimately

We really don't want researchers to think there's a right and wrong - people are different and should use whatever tool works best for their particular needs. If you have reasons to hand-write code, if you read this and aren't convinced, that's fine too. PsychoPy will always provide interfaces to allow scientists to work with the tools on whatever levels work for them. We believe in diversity. 

This post was written because we do want people to make their decision from an informed position.

We, despite being relatively competent programmers, would not dream of writing a study from scratch in hand-written code unless we absolutely had to. But it is a personal choice and, as long as “coders” aren’t looking down on “builders” for their choice, we won’t look down on “coders” either.

