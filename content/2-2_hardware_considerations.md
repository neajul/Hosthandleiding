# 2-2 Hardware considerations

> **TL;DR**
> Basically, any computer that you have previously used as a workstation (for example, an old laptop) can become a server. If it doesn't have an Ethernet port, get an adapter (PCIe Ethernet for a desktop, USB-Ethernet adapter for a laptop). Depending on the scale of your operation, even single board computers like a Raspberry Pi can work, but remember: the only ethical hardware is second hand hardware. Except for hard drives, don't buy second hand hard drives.

## 2-2-1 Picking a machine

> **TL;DR;**
> Basically any computer can be turned into a server, even an old smartphone! For very old or very small computers, you will have to assess if they are fast enough for what you have in mind. If you are reading this guide, any working old laptop is probably enough.

There are a few factors that go into choosing the correct hardware for your project, mainly:

- Budget/availability
- Use case
- Environmental Footprint

The more concurrent users you expect (people that are accessing the server at the same time) the better your hardware needs to be. That being said, most web apps are not very compute intensive and rather rely on having a lot of RAM and the ability to process a lot of requests in parallel—CPUs with multiple cores are definitely beneficial here.

Most well refined systems use PHP, an old and reliable programming language for web that is part of most websites on the internet today. However, since it is an old programming language, it is not very well optimized for a lot of parallel users. Most services that you might want to run on your server specify minimum system requirements, so it's probably good to read up on a few before making a choice.

Some people like to work with single board computers ([[0-2_glossary_of_terms#SBC (Single Board Computer)|SBCs]]), like the Raspberry Pi. While a Raspberry Pi will reach its limits quite quickly if you plan on running several services at the same time, there are other single board computers that are much more powerful and can handle larger operations. Single board computers are often relatively cheap, use very low amounts of energy, and come in a small and convenient form factor.

If the form factor is not important, however, we recommend using an old laptop. Due to much fewer restrictions in terms of size, even an old laptop will likely outperform a new single board computer. The built-in battery, if it is still functional, can protect against fluctuations in the power grid. The built-in screen and keyboard, if still functional, eliminate the necessity for additional peripherals during set up and allow direct interaction with the machine. Due to their portability, laptops are usually designed to be much more power efficient than desktop machines. If you or someone you know doesn't already have an old laptop that you can use, chances are you can find one [[#2-2-3 Where to get old hardware|for free or very cheap]] online.

## 2-2-2 New or Used Hardware

It takes a lot of energy to build computers and buying new hardware has a big impact on the environment. Even the most energy efficient new computer will not be able to offset the amount of energy that had to be used in its production. **We strongly encourage everyone to consider used hardware wherever possible.** A used laptop will always be more environmentally friendly than a new Raspberry Pi!

### 2-2-2a Apple

Most 
While it's certainly possible to install Linux on an old Apple computer like an old MacBook that you or someone you know might have lying around, Apple has complicated this process significantly (basically: the newer your MacBook, the more hurdles you will have to overcome). For the purpose of this guide, we will assume that you have access to an old Windows or Linux computer, as these are much easier and cheaper to come buy than old Apple computers.

If you do have an Apple computer which you aim to install Linux on, there are many guides such as [this one](https://linuxnewbieguide.org/how-to-install-linux-on-a-macintosh-computer/) which will walk you through the installation process. After the installation process is complete, you should be able to follow the guides in this manual as usual.

### 2-2-2c Storage


Hard drives fail. The question is not *if* but *when*. Hard drives have a limited amount of read/write operations they can do before they will inevitably die, and when they do, they probably cannot be fixed (at least not in an economical way). Most servers are always on and especially when you have multiple users, this means that your hard drives will be under a lot of stress. 

- hard drvies vs. ssds
- server grade dhard drives (not necessaryt for at home)





Whether you are using an old laptop or SBC, you probably need to add some additional storage. We strongly recommend setting up a so-called RAID configuration. In very simplified terms this means that you use two hard drives which are perfect copies of each other, so that in case one of your hard drives fails (which it will, given enough time!), you don't lose any data. Additionally, you [[2-4_sofware_considerations#2-4-2 *3-2-1* Backup Rule|might want to get]] an external backup service.

> [!INFO]
> While we recommend buying used hardware wherever possible, we don't recommend this with hard drives. 
> 
> The longer a hard drive is in use, the more likely it is to fail. With used hard drives, it's difficult to know how much life they have left in them. There is also a chance that the second hard drives you find online have been used in crypto mining at some point, further increasing the likelihood of failure in the near future.

Many Single Board Computers run on SD cards by default. SD cards will decrease with every read/write operation and are not suitable mediums for a [[production-ready]] machine! If you want to use a single board computer, make sure you get additional storage to work with.

==something something SSD plus two HDDs, or something similar==





ETHERNET/NETWORK!




## 2-2-3 Where to get old hardware
yes, where?


- something about apple computers
- Used vs. New
- SBCs
- Hard Drives
	- 3-2-1 Backup

==Can we make a flowchart?==

if flowchart; then begin something like this should be considered as steps:
- Storage considerations
	- space vs speed vs cost
		- 5400 < 7200 < ssd < nvme
	- connections
		- usb 2 < usb 3/thunderbolt < sata < m2 (pcie3) < m2 (pcie4)
	- root, database, data
		- / needs fastest
		- /apps has configs,
			- can be same as / but with versioning it is nice to put on separate subvolume/dataset/partition/
		- /db second fastest
		- /data needs the most space
	- RAID?
		- RAID1 (mirroring) is good for redundancy
		- doubles drive cost
