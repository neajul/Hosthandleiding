# System

> When setting up a server, you want to use Linux. And you want to do so without a GUI.

## 2.1 Who's the Penguin?

If setting up [[0-1_glossary#SBC (Single Board Computer)|single board computers]] and [[0-1_glossary#Server|servers]] is not something you do regularly, chances are your knowledge of (non-mobile) operating systems is mostly limited to Apple's macOS and/or Microsoft Windows. When it comes to consumer hardware, both have their advantages and disadvantages (for example that they are proprietary software developed by evil tech conglomerates), but neither are very well suited to run servers. This is where Linux comes in.

Linux is a family of free and operating systems. Open source means that anyone can download and modify the code of Linux and make their own version of it. Because of this, there are countless different versions of Linux, that are commonly called *distros*. While you might not be aware of it, you almost certainly have come in contact with it before, since Android, the operating system that powers most non-Apple smartphones, is based on Linux.

There are many advantages to using Linux over other operating systems, but while its user base has been steadily growing in recent years, on Laptops and Desktop PCs it's probably still a bit of a niche phenomenon. This however is not true at all when it comes to servers: the cloud (more or less) runs on Linux, and for good reasons:

- It's free. That means you can spin up a new server any time without acquiring a license before
- It's secure
- It's stable
- It runs on basically any kind of hardware
- It's customizable: due to its open source character, there are countless *distros*, each with different flavors, features and focuses, and optimized for different scenarios.
- It's lightweight: as opposed to a consumer PC, which should be good at all kinds of things, a server is usually meant to do only one thing, but do that thing really well. Linux gives you the possibility to build an operating system with a focus on one specific task without wasting resources on anything else.

## 2.2 Headlessness

Probably the most prominent example of cutting out unnecessary things is the [[0-1_glossary#Graphical user interfaces, shells, consoles, command-lines and terminals|GUI]], or rather the lack thereof. We are used to interacting with so-called graphic user interfaces: Windows, Mouse cursors, background images, things to be dragged into folders that contain them, etc. This great to organize photos, browse the web, watch movies. But it also costs a lot of resources. We don't want to have the same level of interaction with a server. We want it to sit in a room somewhere, headless (meaning without a screen, keyboard and mouse connected to it), doing its job. 

This is why most servers run on operating systems that have reduced their interfaces to the bare minimum: a text based console. You type in a command, the server gives a response—all via text, like in the old days.

To many, the command line still has an air of [Y2K-action-movie-hacker](https://hackertyper.com/) to it, and it can seem a bit daunting. And it does take a bit of getting used to—sometimes it can be disorientating or confusing. Things that take a simple gesture on a consumer PC suddenly take multiple commands and a lot of troubleshooting. But once you got the hang of it, you will realize that it's actually far more powerful than the GUIs we normally interact with.

Currently, the scope of this wiki has not yet allowed us to write an in-depth guide to  the command line. We would like to do this in the future, though. For now, we will just tell you to search the internet for things like "command line for beginners", you will find countless guides [such as this one](https://scrapism.lav.io/intro-to-the-command-line/) that should give you a pretty good overview. Further than that, we think the best way to learn these kinds of things is to get your hands dirty and follow one of our [[3-1_installing_linux|guides]].

## 2.3 DietPi

As mentioned above, there are countless Linux Distributions, each with their own sets of pros and cons. In our guide, we recommend DietPi: originally developed as a lightweight system for the Raspberry Pi, it now supports most SBCs as well as native PCs. It has an active community, is straight forward, and super light weight, meaning that it's very reduced in functionality and that it will use very few resources.

There are many other distros that can make sense, depending on preference and situation. If you prefer something else, feel free to install that instead; since our guides recommend using docker, you should be able to follow along nonetheless.