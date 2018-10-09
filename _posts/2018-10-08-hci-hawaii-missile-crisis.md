---
layout: post
title:  "HCI: Hawaii Missile Crisis"
date:   2018-10-08 13:00:00 -0700
category: [human computer interaction]
---
Taking a class for Human-Computer Interaction and having a crisis in Hawaii due to lack of basic HCI principles made us realize how important our role as designers are to the world. 

<!--more-->

## First Experience
I started actually observing human-computer interaction in a course called Informatics 131 at UCI, taught by Professor Matthew Bietz. 

> IN4MATX 131. Human Computer Interaction. 4 Units.<br/>
> Basic principles of human-computer interaction (HCI). Introduces students to user interface design techniques, design guidelines, and usability testing. Students gain the ability to design and evaluate user interfaces and become familiar with some of the outstanding research problems in HCI.<br/>
> [UCI Informatics Course Catalogue](http://catalogue.uci.edu/allcourses/in4matx/)

This class focused on the "academic" part of human-computer interaction; teaching students how to evaluate software and relate the effects of technology on the human psyche. The following course, Informatics 132, continued to apply the teachings, study, evaluate, and re-design a live application (to which I had chosen Spotify).



### Hawaii Incident
    BALLISTIC MISSILE THREAT INBOUND TO HAWAII. SEEK IMMEDIATE SHELTER. THIS IS NOT A DRILL

On January 18, 2018, a false ballistic missile alert was sent over the Emergency Alert System all over Hawaii. Although it is generally seen as caused by human error, there was some flaws in the design of the application; we saw, as computer science students, the role of user interfaces and how it can cause panic throughout an entire state. 38 minutes after the initial alert, a second alert was sent:

    There is no missile threat or danger to the State of Hawaii. Repeat. False Alarm.

Although people were assured via email and Twitter as early as 13 minutes after the alert, it took roughly 32 minutes (8:13 - 8:45) to send a custom message with Hawaii Emergency Management Agency. Experts say it will take 20 minutes for a ballistic missile to reach Hawaii. The following is what the interface _could_ have looked like; both are recreations, as they claim original screenshots would be a security risk.

![](https://pbs.twimg.com/media/DTuDI2bVoAEC2tK.jpg)

The interface for Emergency Management lacked some of [Jakob Nielson's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/):
 - **User control and freedom**: not allowing users to create and send custom messages, such as the false alarm. The agency was forced to create a new "template" for false alarms, and use that to issue the alert.
 - **Error Prevention**: More accurately, a "action-based slip". The operator (supposedly, as some confusion arose weeks after) selected the actual drill "PACOM(CDW) - STATE ONLY" instead of the drill, "DRILL - PACOM(CDW) - STATE ONLY"
 - **Visibility of System Status**: It took roughly 10 minutes for staff at the Emergency Agency, including the operator who sent the initial alert, to recognize that the alert was _not_ a false alarm. 

## Designing To Avoid Errors
It may seem obvious now looking at the user interface that there are many things that can be done to ensure that this slip does not happen: adding a high-intensity confirmation screen for real alerts versus a simpler one for drills and separating the buttons to make it clear which are drills and which are not. As of today, Hawaii Emergency Agency now requires _two_ employees to be present to issue a state-wide alert, simply making it less likely for a slip. 

#### Side Note: Slips vs Mistakes

A "Slip" is when the user intends to do one thing, and instead does another on accident: the users assumptions and goals are correct. An example would be: You are leaving your house, and grab the wrong set of keys because they were next to each other. You intended to get the right set, but accidentally did the wrong action. 

A "Mistake" on the other hand, is when the users intentions or goals are incorrect. For this missile crisis, a _mistake_ would have been if the operator actually thought there was a missile inbound, and their action, setting off a state alert, would be correct based on those assumptions.


## Designing For Errors


Although there is some evident fault with the user interface, there is a certain amount of human responsibility by management and operators of the system. With humans, slips or mistakes are inevitable, and recovering from those errors. Implementing a "template" that will allow operators to send _any_ message would allow a false alarm message to be sent immediately after they discover the error. Furthermore, **visibility of system status** by creating an understandably more urgent alarm, notification, or confirmation screen upon selecting live alerts, will allow errors to be discovered easily. 



More detailed analysis and explanation for this missile crisis can be found [here](https://medium.com/@scottrob/human-centered-design-and-the-missile-false-alarm-in-hawaii-6b2d76ac2db).
<br />
<br />

---
<br /><br />
After this crisis, we explored more applications for human computer interaction, from serious cases such as airplane landings having good user interfaces to ensure safe flight and landing, and everyday devices such as keyboards or popular applications such as browsing and text editors. I started observing HCI influences in the products I use, and the motivation for improving usability or consequences for their disregard.