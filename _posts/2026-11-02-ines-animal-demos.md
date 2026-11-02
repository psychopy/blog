---
layout: single
title:  "Using PsychoPy in animal research"
date: 2026-11-02 11:00  
category: PsychoPy
tags: psychopy animal behaviour rodents mice rats zebrafish demos 
author: Inés
author_profile: true
---

# Using PsychoPy to create animal behaviour paradigms
Animal behaviour research aims to understand how different animals interact with each other and their environment, whilst behavioural neuroscience investigates the mechanisms underlying such interactions, how they might be impaired in different scenarios or under different disorders, and how different treatments or interventions might prevent or reverse such impairments.

Behaviour can be studied simply by observing animals in their natural environment, but this offers limited insight into underlying physiological processes. More targeted paradigms allow direct measurement; for example, the novel-object-recognition test investigates short-term memory by exploiting rodents' natural curiosity: usually, animals spend more time investigating a novel object than a familiar (previously-presented) one, but this does not happen if they have already forgotten about the familiar one.

Most assume animal behavioural paradigms require expensive and niche material, such as operant chambers or very cumbersome and complex coding. However, whilst learning and cognitive tasks do need specialised systems, many paradigms investigate innate responses to stimuli that can be built in PsychoPy. You only need a camera and a projector or speaker; that's easy!

As part of my PhD Placement with Open Science Tools, I  developed a set of animal behavioural experiment demos, each based on published methodologies and adaptable across research questions and species. Full documentation and references are included with each demo:
- [Looming visual stimulus demo](https://pavlovia.org/InesJP/Looming-visual-stimulus)
- [Optomotor (or optokinetic) assay demo](https://pavlovia.org/InesJP/Optomotor_assay)
- [Acoustic startle demo](https://pavlovia.org/InesJP/Acoustic_startle)
- [Zebrafish hunting assay demo](https://pavlovia.org/InesJP/Hunting_assay)
- [Zebrafish predator fear task demo](https://pavlovia.org/InesJP/Predator_fear_task)


# About the stimuli and behaviours
Through this project, I learned about a range of rodent and zebrafish behaviours and the stimuli used to study them.

Some stimuli trigger similar physiological responses across species. For example, a [looming visual stimulus](https://pavlovia.org/InesJP/Looming-visual-stimulus "Link to demo") mimics an approaching predator and triggers a escape response in [zebrafish](https://www.cell.com/current-biology/fulltext/S0960-9822(15)00667-3?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0960982215006673%3Fshowall%3Dtrue "Link to primary article") and defensive behaviours in [mice](https://pmc.ncbi.nlm.nih.gov/articles/PMC3809337/#F3 "Link to primary article").

The same is true for the [optomotor assay](https://pavlovia.org/InesJP/Optomotor_assay "Link to demo"). In free-swimming zebrafish, it elicits a [reflective swimming towards the direction of motion](https://www.jneurosci.org/content/23/9/3726.full "Link to primary article"), and if shown 360º around a restrained fish, it becomes an optokinetic assay driving [directive fictive swimming](https://www.jneurosci.org/content/43/22/4062 "Link to primary article"). The same separation applies to mice, with free-moving mice being tested in [optomotor assays](https://www.nature.com/articles/s41598-018-27329-w#Sec7 "Link to primary article") and head-fixed in [optokinetic assays](https://pmc.ncbi.nlm.nih.gov/articles/PMC2323102/ "Link to primary article").

The [startle response](https://pavlovia.org/InesJP/Acoustic_startle "Link to demo"), triggered by loud noise, vibration, or bright light, is also conserved across species. This demo follows a [mice protocol](https://pubmed.ncbi.nlm.nih.gov/30001725/ "Link to primary article") that uses white noise and also tests prepulse inhibition: the reduction in startle response when a softer acoustic stimulus precedes it, which is a proxy for the ability to filter irrelevant sensory information. Zebrafish also experience [startle responses](https://www.sciencedirect.com/science/article/pii/S0165027002001188 "Link to primary article") (they take a C-bend body shape) and [prepulse inhibition](https://journals.biologists.com/jeb/article/216/18/3504/11613/Auditory-sensitivity-of-larval-zebrafish-Danio "Link to primary article"), so this demo can easily be adapted for them.

Other behaviours are more species-specific. Zebrafish larvae naturally hunt paramecia, so free-swimming hunting behaviour can be studied by feeding them while recording. However, many experiments (imaging, electrophysiology, optogenetics) require restrained larvae. Since zebrafish respond to small moving dots with a [hunting response](https://www.frontiersin.org/journals/systems-neuroscience/articles/10.3389/fnsys.2011.00101/full#s1 "Link to primary article"), this can be used to study hunting behaviour in restrained larvae. I have replicated this hunting assay in this [PsychoPy demo](https://pavlovia.org/InesJP/Hunting_assay "Link to demo").

In addition, zebrafish are preyed upon by the Indian leaf fish, and showing its image can elicit a [fear response](https://www.sciencedirect.com/science/article/pii/S0166432807003981 "Link to primary article"). I have created a demo of this aversive response, found [here](https://pavlovia.org/InesJP/Predator_fear_task "Link to demo"), based on a [follow-up study](https://www.sciencedirect.com/science/article/pii/S0166432809001491#bib3 "Link to primary article").


# Have a go!
You can download the demos, modify them as needed, and run them in your own setup. Let us know if you have any questions or suggestions! We are always available in [Discourse](https://discourse.psychopy.org/).

You can also create your own animal behaviour experiments and make them available to the rest of the users to help the scientific community. A few months ago we ran a [workshop](https://workshops.psychopy.org/ "Official PsychoPy Workshops page") on how to create experiments for rodent learning; you can find its openly available material [here](https://drive.google.com/drive/folders/15CMuKKz7fgNBhbL9GanTL5jgxW_gnUad). Have fun!
