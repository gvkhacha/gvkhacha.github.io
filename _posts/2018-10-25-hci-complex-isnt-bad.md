---
layout: post
title:  "HCI: Complexity Isn't Bad"
date:   2018-10-25 13:00:00 -0700
category: [human computer interaction]
---

Many people consider "User Interaction" to be based solely off the idea that the interface for a program/device should be easy to use. While that may be the case, there is always a trade off (something we get reminded of often in computer science). 

<!--more-->


## Trade offs
So far in my three years of education at UCI, I learned that the most common answer for any question is ~~C~~ it depends. 

> Which data structure should I use? 

Well, it depends on what you value: insertion, deletion, order, sorting, searching, etc. A HashTable seems amazing but the trade-off there is it becomes difficult to traverse it in an ordered way.

> Is C++ better than Python?

~~Yes~~ Well, it depends on if you value reading and writing code quickly with less overhang versus performance and micromanagement. There are sacrifices you make for each decision and each value. With Python, we sacrifice speed and efficiency to quickly write programs.

---

That same idea extends to HCI. Are easy-to-learn interfaces better than any other? Well, it depends on who you're designing it for, and what your expectations of them are, and ultimately, what _they_ value. Turns out, for everyday devices to the public, a lot of people value plug-and-play devices and applications that they can get accustomed to very quickly. After all, when you learned to drive the first time, did you consider how turning the ignition sparked the combustion cycle of an engine and the movement of gears? Probably not, but if you have to drive manual transmission, or end up doing some repairs, you'd end up learning whats going on behind-the-scenes.

<image style="float:right;" src="https://i.stack.imgur.com/iTJri.jpg" />

## Sometimes, we need complexity

Regarding the airplane cockpit below, I don't think it is, by any standard, is easy to learn. Now, that's not to say it isn't easy to _use_, or especially not user-friendly. As you might expect, there is a lot going on to the design of every control in the cockpit: from position of gauges and controls, to colors, and even shapes (the lever to lower the wheels look and feel like wheels!). 


Should every user be able to sit in the cockpit and understand how to use it? Ofcourse not, and we shouldn't expect designers to create the system for that. They work on the assumption that whoever uses the system will undergo training in order to use it, and are comfortable enough to know each control. With that in mind, we can spread everything out and have all information and control in view of the pilots, ready at a moment's notice. 

## Other times, simplicity is bliss

There may be some basic functions that every user should do. Imagine on an operating system, opening and moving files is a task every user _should_ be able to do. Fairly simple, and at this point, we have established a convention of double-clicking to open files and drag & drop mechanics. 

![](https://www.digitalcitizen.life/sites/default/files/gdrive/win_drag_drop/drag_drop_1.png)

Fairly simple right? I can move one file, multiple files, all files, depending on how I select them. So, is this a good system? Well, probably. There are many benefits to this:
* You see which files you're moving, and 100% sure you're moving the "right" files
* You see where you are moving it
* Easy reversal of actions! If I find this is wrong, I can drag/drop back (Even Ctrl+Z sometimes!)


<image style="float:right;" src="http://s3.media.squarespace.com/production/717498/8416204/_jDnzGifeffM/TG6wv9KRoqI/AAAAAAAAAS8/zGjZrmmD2vQ/s400/procon.jpg" />

### So what's in the CON section?


Let's think use cases. I want to move a file from `/folder/subfolder3/helpme/pics/hello.txt` to `/anotherfolder/subfolder1/textfiles/helpme/hello.txt`. Not only do I have to open the first folder, double clicking a bunch of folder icons until I reach the folder I want, but I have to open another "Finder" or file manager and do the same to the second directory. Lots of precious seconds lost.

Not good enough for you? Okay. Another use case. I want to move all files that have the characters "doc" in the name but not in the extension? In a folder with 1000 files? 
`mv *doc*.* /folder/subfolder2/`

There may be more examples, but the more complex it gets, the harder it becomes to do with GUI file managers, and "easier" with command line interfaces or scripts. (Given you know the command line, there _is_ a learning curve)

### So which ones better?

Just like all those other answers, **_it depends_**. Sometimes, you really want to grab your mouse and highlight the files to move them. Other times, you don't want to take your hands off the keyboard to open the folders, and do all those "extra" steps, so we open up a terminal and type the commands. Me personally, I use both, since I'm still on that learning curve that I might have to search around for the right command and arguments. 