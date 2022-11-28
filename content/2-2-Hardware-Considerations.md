# TL;DR
use whatever computer you previously used as your workstation. If it has an Ethernet port, you're good to go. If not, get a PCIe Ethernet card (for a desktop) or a USB-Ethernet adapter (for a laptop).

# 2.2 Hardware Considerations
## 2.2.1 Picking a machine
Basically any computer can be turned into a server. For very small or very old computers you might have to check if they are fast enough, but basically an old laptop should be able to do most things that you need. Some things you can also do with a single board computer ([[0.2 Glossary of Terms#SBC (Single Board Computer)|SBCs]]) like a Raspberry Pi, even though that depends on the scope of what you want to do.
- ==@Ada could you write a short bit on how to pick appropriate hardware for whatever scale you want to be working on?==
Which type of hardware you pick depends on a few factors but can be divided into two sections:

- Budget/availability
- Use case

With both of these aspects there are further considerations to take into account, to narrow down the search

- What will you be hosting?
	- In other words, which cloud services will you be replacing with your own?
	- Most well refined systems use PHP, an old and reliable programming language for web that is part of most websites on the internet today. However, since it is an old programming language, it is not very well optimized for a lot of parallel users. One system that we will recommend, Nextcloud, is built partly using PHP, which limits the scalability on hardware with a small amount of RAM. There are ways around this though that we will get into in section [3.1](obsidian://open?vault=Hosthandleiding&file=content%2F3.1%20Practical%20Guides%20and%20configs)
- How many people will be using the system?
	- The more concurrent users (users that are accessing the server at the same time) the better the hardware needed. That being said, most web apps are not very compute intensive and rather rely on having a lot of RAM and the ability to process a lot of requests in parallel.
	- The more devices every person have connected to the system, the higher the system load.
- 

## 2.2.2 New or Used Hardware
It takes a lot of energy to build computers and as such buying new hardware has a big impact on the environment. Even the most energy efficient new computer will not be able to offset the amount of energy that had to be used in its production. As such, we strongly encourage everyone to consider used hardware wherever possible! Using a used laptop will always be more environmentally friendly than a new Raspberry Pi!

Depending on where you live, you should be able to find old laptops on used marketplaces for cheap to almost-free.

### 2.2.2a Apple
While it's certainly possible to install Linux on an old Apple computer like an old MacBook that you or someone you know might have lying around, Apple has complicated this process significantly (basically: the newer your MacBook, the more hurdles you will have to overcome). For the purpose of this guide, we will assume that you have access to an old Windows or Linux computer, as these are much easier and cheaper to come buy than old Apple computers.

If you do have an Apple computer which you aim to install Linux on, there are many guides such as [this one](https://linuxnewbieguide.org/how-to-install-linux-on-a-macintosh-computer/) which will walk you through the installation process. After the installation process is complete, you should be able to follow the guides in this manual as usual.

### 2.2.2c Storage
Whether you are using an old laptop or SBC, you probably need to add some additional storage. We strongly recommend setting up a so-called RAID configuration. In very simplified terms this means that you use two hard drives which are perfect copies of each other, so that in case one of your hard drives fails (which it will, given enough time!), you don't lose any data. Additionally, you [[2.4 Sofware Considerations#2.4.2 "3-2-1" Backup Rule|might want to get]] an external backup service.

> ⚠️ While we recommend buying used hardware wherever possible, we don't recommend this with hard drives. The longer a hard drive is in use, the more likely it is to fail. With used hard drives, it's difficult to know how much life they have left in them. There is also a chance that the second hard drives you find online have been used in crypto mining at some point, further increasing the likelihood of failure in the near future.

Many Single Board Computers run on SD cards by default. SD cards will decrease with every read/write operation and are not suitable mediums for a production-ready machine! If you want to use a single board computer, make sure you get additional storage to work with.

==something something SSD plus two HDDs, or something similar==

## 2.2.3 Where to get old hardware
yes, where?


- something about apple computers
- Used vs. New
- SBCs
- Hard Drives
	- 3-2-1 Backup

==Can we make a flowchart?==