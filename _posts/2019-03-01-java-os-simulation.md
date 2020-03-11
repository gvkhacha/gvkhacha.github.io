---
layout: post
title:  "Java: Operating System Simulation"
date:   2019-03-01 13:00:00 -0700
category: [programming]
---

As one of the two-week projects in a programming concepts course, we were assigned to create an operating system simulation using Java and a Java GUI library of our choice. The simulation does not focus on the tasks of an OS, but rather the implementation of concurrent systems and proper threading.

<!--more-->

## The project

<image style="float:right;width:50%;height:auto;margin-left:10px;" src="/assets/img/141os.png" />

To demonstrate concurrent programming in Java, our project involved creating a simple simulation consisting of three main parts: Users, Disks, and Printers. There can be multiple users, disks, and printers, and should have as much simultaneous actions as possible. There is only three operations supported as well: read to disk, write to disk, and print file. 


The graphical user interface shows data in the disk, the printer(s) read and printing to different interfaces, and a speed change slider.

### Managers

To help implement concurrent devices, the simulation employed managers for each device. User managers, responsible for handling and swapping input between the different users. Disk managers, responsible for taking read/write commands and dispersing them between disks, ensuring users read the proper files. Finally, Printer managers take a print job and assign it to a printer.

### Variability

The simulation supports any number of disks, users, and threads, along with length of files, and speed of the simulation. These variables show us when bottlenecks could occur in a simple "operating system." For example, when only one read/write operation could be completed at a time, many users or printers are stagnant. Instead, switching between users and printers accordingly to read/write different parts of the disk.

## Design Flaws

My design for the project was deeply flawed in that it did not correctly implement a model-view-controller design. Instead, I used Java Swing fully implemented with the resource classes, and as such, they could not be used with different graphical user interfaces and greater difficulty with bug fixing and feature additions. 

If I were to redo this project, I would have a full command line interface for the simulation, which will encourage me to separate the resources, managers, and threads from the user interface. 