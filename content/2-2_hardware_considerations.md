# 2-2 Hardware considerations

> **TL;DR**
> Basically, any computer that you have previously used as a workstation (for example, an old laptop) can become a server. If it doesn't have an Ethernet port, get an adapter (PCIe Ethernet for a desktop, USB-Ethernet adapter for a laptop). Depending on the scale of your operation, even single board computers like a Raspberry Pi can work, but remember: the only ethical hardware is second hand hardware. Except for hard drives, don't buy second hand hard drives.

## 2-2-1 System Requirements

There are a few factors that go into choosing the correct hardware for your project, mainly:

- Budget/availability
- Use case
- Environmental Footprint

The more concurrent users you expect (people that are accessing the server at the same time) the better your hardware needs to be. That being said, most web apps are not very compute intensive and rather rely on having a lot of RAM and the ability to process a lot of requests in parallel—CPUs with multiple cores are definitely beneficial here.

Most well refined systems use PHP, an old and reliable programming language for web that is part of most websites on the internet today. However, since it is an old programming language, it is not very well optimized for a lot of parallel users. Most services that you might want to run on your server specify minimum system requirements, so it's probably good to read up on a few before making a choice.

## 2-2-2 Picking a machine

Basically any computer can be turned into a server, even an old smartphone! For very old or very small computers, you will have to assess if they are fast enough for what you have in mind. If you are reading this guide, any working old laptop is probably enough.

Some people like to work with single board computers ([[0-1_glossary_of_terms#SBC (Single Board Computer)|SBCs]]), like Raspberry Pis. While a Raspberry Pi will reach its limits quite quickly if you plan on running several services at the same time, there are other single board computers that are much more powerful and can handle ever larger jobs. Single board computers are often relatively cheap, use very low amounts of energy, and come in a small and convenient form factor.

If the form factor is not important, however, we recommend using an old laptop. Due to much fewer restrictions in terms of size, even an old laptop will likely outperform a new single board computer. The built-in battery, if it is still functional, can protect against fluctuations in the power grid. The built-in screen and keyboard, if still functional, eliminate the necessity for additional peripherals during set up and allow direct interaction with the machine. Due to their portability, laptops are usually designed to be much more power efficient than desktop machines. If you or someone you know doesn't already have an old laptop that you can use, chances are you can find one [[#2-2-3 Where to get old hardware|for free or very cheap]] online.

## 2-2-3 New or Used Hardware

It takes a lot of energy to build computers, and buying new hardware has a big impact on the environment. Even the most energy efficient new computer will not be able to offset the amount of energy that had to be used in its production. **We strongly encourage everyone to consider used hardware wherever possible.** A used laptop will always be more environmentally friendly than a new Raspberry Pi!

### Apple

While it's certainly possible to install Linux on an old Apple computer like an old MacBook, and to turn it into a server, Apple has complicated this process significantly (basically: the newer the computer, the more hurdles you will have to overcome). Because the process changes so much depending on your model, we currently have not included a manual for how to install Linux on old Apple computers. 

For the purpose of this guide, we will assume that you have access to an old Windows or Linux computer, as these are much easier and cheaper to come buy than old Apple computers. If you do have an Apple computer which you want to install Linux on, there are many guides such as [this one](https://linuxnewbieguide.org/how-to-install-linux-on-a-macintosh-computer/) which will walk you through the installation process. After the installation process is complete, you should be able to follow the guides in this manual as usual.

## 2-2-5 Storage

No matter what hardware you chose, you will often need to add additional storage, for example if you want to set up a file sharing service where each user has multiple Gigabytes or even Terabyte of storage allocated to them. But also in other cases, it's quite common to use different storage options for different purposes. A classic solution would be to use a small but fast disk to run your operating system from, and to save all the user data on a bigger, but potentially slower drive. There are multiple considerations here, but mainly it boils down to **speed**, **capacity**, **durability** and **expense**.

Most computers come with some built in storage on which the system is installed, but depending on what you want to do, this might not be enough to run a server. There are multiple considerations here, but mainly it boils down to **speed**, **capacity**, **durability** and **expense**.

### Types of storage

>**TL;DR;**
>HDDs are very cheap but slow and not durable. SSDs are fast and reliable, but expensive. In most cases, a hybrid solution is the most efficient: run the system on a small SSD that is fast and reliable, and store all data on multiple large and cheap HDDs.

The main types of storage are Hard Disk Drives(HDD) and Solid State Drives (SSD), though some single board computers also work with other storage mediums like **flash drives** or **SD cards**. While those are ok for testing and tinkering, it is not recommended to run a server that uses an SD card as data storage—SD cards deteriorate with every read/write operation, and they **will** fail eventually, leading to downtime and potentially data loss. It is possible to use an SD card to boot the system from, but to set it to read-only, and store all relevant data on another volume, but this is something that we will not cover in this guide as it is a bit of an edge case.

#### Hard Disk Drives (HDD)

Hard Disk Drives have been around for a long time. Simply put, they operate similar to a CD or DVD, with all data stored on a physically spinning disk. They are the slowest, type of storage, but also the cheapest. They are very big in comparison to other solutions and not very durable: Hard drives have a limited amount of read/write operations they can do before they will inevitably die, and when they do, they probably cannot be fixed without spending a considerable amount of money. Most servers are always on and especially when you have multiple users, this means that your hard drives will undergo a lot of read/write operations. **The question is not *if* an HDD will fail, but *when*.** 

There are server-grade HDDs which are more resistant to wear, but cost more money. For the scope of self-hosting, those are probably not required, though. Even under continuous use, a new HDD should last a few years, and there are setups to prevent data loss even in case of an HDD drying.

> [!WARNING]
> While we recommend buying used hardware wherever possible, we don't recommend this with HDDs. 
> 
> The longer a hard drive is in use, the more likely it is to fail. With used hard drives, it's difficult to know how much life they have left in them. There is also a chance that the second hard drives you find online have been used in crypto mining at some point, further increasing the likelihood of failure in the near future.

##### RAID configurations

Nothing good lasts forever, and that is especially true for HDDs. In anticipation of hard drive failure and data loss, you probably don't want to save all your data on one HDD. Fixing or recovering data from an old hard disk is magnitudes more expensive than a new disk, and not guaranteed to work. Instead, it's recommended to set up what is called a RAID configuration.

In layman's terms, this means that multiple hard drives are set up in such a way that every piece of data is present on multiple disks, so that if one of the drives fails, no data is lost, and it can simply be replaced. The most simple RAID configuration is RAID-0, which is two hard drives that are exact mirrors of each other. Every time data is written to one of the drives, it's written to the other one as well. If one of the drives fails, you can simply exchange it without any data lost.

Obviously, this doubles the cost of storage, as you will have to buy double the amount of hard disks. But, especially if you plan to set something up for multiple users with the goal of maintaining service for a long period of time, you should seriously consider this. Also, (at the point of writing) two HDDs are still cheaper than the equivalent amount of storage on an SSD.

##### Network Attached Storage (NAS)

While you can set up your own RAID configuration with multiple hard drives, there are many solutions out there that do exactly this already, the most popular ones are probably by the brand Synology. They are actually small servers themselves that can connect to your computer over USB or Ethernet, and can hold multiple hard disks. Depending on where you live, you might be able to find a second hand NAS for relatively cheap online, potentially saving you time and effort. If one of the drives in your NAS fails, simply replace it with a new one.

#### Solid State Drives (SSD)

**Solid State Drives** are a newer technology than HDDs that address most of their shortcomings: they are much smaller, much faster and much more durable. They are, however, also much more expensive. Unless money is not a facotr for you, it's probably not very feasible to use SSDs to store large amounts of data. SSDs are however the preferred medium to run an operating system from, as this will have a big impact on performance while requiring relatively little space. As opposed to HDDs, SSDs are probably safe to buy second hand.

## 2-2-6 Network connection

While it's certainly possible to run a server over Wifi, Ethernet is much faster and much more reliable. Unless you really don't have access to an Ethernet port we would always recommend you to connect your server to the internet over Ethernet. Most single board computers and Windows laptops come with Ethernet ports, if you have a computer without one, you should probably look into finding an adapter!

## 2-2-7 Where to get old hardware

Computers quickly lose value. Improvements in performance and capacities quickly render older machines obsolete, and computers that are older than 10 years often can't even receive updates anymore. This means that very few people would invest much money into old hardware, which keeps the prices low. This is good news for the happy self-hoster, because the requirements for self-hosting are comparatively low.

With a little bit of luck, on websites like Marktplaats (in the Netherlands) and eBay (in many other parts of the world) it should be possible to find old laptops for cheap or even for free. It's also worth asking in your friend circle and/or professional environment if people have old computers that they don't use anymore. 
