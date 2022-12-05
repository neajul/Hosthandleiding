# Glossary

Much of this information has been taken from the simple English Wikipedia. It's a bit of an incomplete list and a work in progress.

## Booting

Booting is what happens when a computer starts. This happens when the power is turned on. It is called "reboot" if it happens at other times. When you boot a computer, your [[#CPU (Central Processing Unit)|processor]] looks for instructions in system ROM (Read only memory, the BIOS) and executes them. They normally wake up peripheral equipment and search for the boot device. The boot device either loads the operating system or gets it from someplace else. 

## CPU (Central Processing Unit)

A central processing unit (CPU) is an important part of every computer. The CPU sends signals to control the other parts of the computer, almost like how a brain controls a body.

## ARM

ARM architecture is a computer CPU architecture used in computers of all sizes up to supercomputers; commonly used in embedded systems and mobile devices such as cell phones, tablet computers, and handheld game consoles such as the Game Boy Advance. 

ARM CPUs use very little electricity and produce very little heat. Most ARM CPUs run on battery power and don't need a cooling fan. The Linux operating system is used most on ARM CPUs.

## x86

x86 is a term used to describe a CPU instruction set compatible with the Intel 8086 and its successors, including the Pentium and others made by Intel and other companies. 

This is the CPU architecture used in most desktop and laptop computers. Many 21st century workstations and servers also use x86 processors.

## SBC (Single Board Computer)

A single-board computer (SBC) is a complete computer built on a single circuit board, with microprocessor(s), memory, input/output (I/O) and other features required of a functional computer. Single-board computers are commonly made as demonstration or development systems, for educational systems, or for use as embedded computer controllers.

---

## File Systems

A File system (or filesystem) is a way of storing all data on a data storage device. The data is usually organized in computer files in directories. Below the file system there is usually a physical device where the files are stored. 

This might be a hard disk, USB flash drive, compact disc, or DVD. The file system might also talk to a remote server over a network where the file is stored. The file system might also only use RAM to store the files.

## Kernel

A kernel is the central part of an operating system. It manages the operations of the computer and the hardware, most notably memory and CPU time.[1] Kernels also provide services which programs can use through system calls. 

## Linux

Linux or GNU/Linux is a Unix-like operating system (or family of) for computers. An operating system is a collection of the basic instructions that manage the electronic parts of the computer allowing running applications and programs. 

The Linux kernel (the basis of the operating system) is free software, meaning everyone has the freedom to use it, see how it works, change it, or share it. 

## Ubuntu

Ubuntu is a free operating system that uses the Linux kernel. The word "ubuntu" is an African word meaning "humanity to others". It is pronounced "oo-boon-too".

It is one of the most popular Linux distributions and it is based on Debian Linux computer operating system. 

## Debian

Debian is a free operating system. It is a distribution of an operating system known as the GNU operating system, which can be used with various kernels, including Linux, kFreeBSD, and Hurd. In combination with these kernels, the operating system can be referred to as Debian GNU/Linux, Debian GNU/kFreeBSD, and Debian GNU/Hurd, respectively. Debian GNU/Linux is one of the most complete and popular GNU/Linux distributions, on which many others, like Ubuntu, are based. 

## GNU (GNU's Not Unix)

GNU is the name of a computer operating system. The name is short for GNU's Not Unix. Richard Stallman leads the GNU Project. The popular Linux operating systems made using the Linux kernel have many GNU tools too. So, many projects and developers call the Linux-based operating systems GNU/Linux.

The GNU project was started by Richard Stallman in 1983. He wanted to create a computer system that was all free and open-source software. Users could change, share and publish new work based on GNU. He and a group of developers started by creating copies of each piece of UNIX software. The rest of GNU was the kernel, called the GNU Hurd, which is not yet finished. The more popular Linux kernel is often used instead. 

## DietPi

DietPi is an extremely lightweight Debian-based OS. It is highly optimised for minimal CPU and RAM resource usage, ensuring your SBC always runs at its maximum potential.

## Docker (software)

**Docker** is a technology that bundles a software program with all of the other software that application needs to run, such as an operating system, third-party software libraries, etc. Software bundled like this is called a **container**.

The benefit of using Docker to put applications in containers is that they can be run on different kinds of computers (for example, both a laptop and a web server), without the risk of a missing software library or a different operating system causing the application to not work.

---

## Graphical user interfaces, shells, consoles, command-lines and terminals

Computers can display information and let the user give commands to it using two methods: a command line interface (CLI) or a graphical user interface (GUI).

In a command line interface, the user types commands using the keyboard to tell the computer to take an action. For example, the more command available in most operating systems will display the contents of a file. Sometimes people call CLI “Console”, but consoles can be GUI, too. 

## Shell

An operating system shell is a user interface that enables the user to interact with and access the services offered by the operating system. The user gives commands to the operating system through its shell.

There are various types of shells:

- Command line shells: the user types commands at the prompt.
- Menu driven shells: the user selects commands from menus.
- Graphical user interface shells: the user selects  graphical menus and icons.

Examples of command line operating systems are UNIX and Disk Operating System (DOS). Examples of menu driven operating systems are the DOS shell. Finally, examples of graphical user interface (GUI) operating system are Linux and Microsoft Windows. 

## Sytem Console

One meaning of system console, computer console, root console, operator's console, or simply console is the text entry and display device for system administration messages, particularly those from the BIOS or boot loader, the kernel, from the init system and from the system logger. 

It is a physical device consisting of a keyboard and a screen, and traditionally is a text terminal, but may also be a graphical terminal. System consoles are generalized to computer terminals, which are abstracted respectively by virtual consoles and terminal emulators. 

## Text Terminal

A text terminal, or often just terminal (sometimes text console) is a serial computer interface for text entry and display. Information is presented as an array of pre-selected formed characters. When such devices use a video display such as a cathode-ray tube, they are called a "video display unit" or "visual display unit" (VDU) or "video display terminal" (VDT).

The system console is often a text terminal used to operate a computer. Modern computers have a built-in keyboard and display for the console. Some Unix-like operating systems such as Linux and FreeBSD have virtual consoles to provide several text terminals on a single computer. 

## Command Line Interface (CLI)

A means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines). 

## Linux Console

The Linux console is a system console internal to the Linux kernel.[1] A system console is the device which receives all kernel messages and warnings and which allows logins in single user mode.

## Command Line Cheat Sheets

A list of cheat sheets for different command-lines environments.

- [Linux Cheat Sheet](https://github.com/sudheerj/Linux-cheat-sheet)
- [Mac OS Terminal Cheat Sheet](https://gist.github.com/cferdinandi/ef665330286fd5d7127d)
- [Bash Cheat Sheet](https://github.com/RehanSaeed/Bash-Cheat-Sheet)
- [SSH Cheat Sheet](https://github.com/raghuboosetty/cheatsheets/blob/master/ssh.md#ssh)

---

## Server

In computing, a server is a piece of computer hardware or software (computer program) that provides functionality for other programs or devices, called "clients". This architecture is called the client–server model. Servers can provide various functionalities, often called "services", such as sharing data or resources among multiple clients, or performing computation for a client. 

A single server can serve multiple clients, and a single client can use multiple servers. A client process may run on the same device or may connect over a network to a server on a different device. Typical servers are database servers, file servers, mail servers, print servers, web servers, game servers, and application servers.

## Cloud

The cloud is a metaphor for the Internet based on how it is described in computer network diagrams. Just as how in the real world, clouds hide parts of the sky from sight, the cloud in computing hides the complex infrastructure that makes the Internet work. 

## Software as a Service (SaaS)

Software as a service is a software licensing and delivery model in which software is licensed on a subscription basis and is centrally hosted. SaaS is also known as "on-demand software" and Web-based/Web-hosted software.

## Web hosting service

A web hosting service is a type of Internet hosting service. It allows people and companies to make their website available on the World Wide Web. Web hosts are companies which provide space on a server which is owned or leased for use by clients. These clients store their Web site on the server. The server feeds the web pages to the Internet. 

## Domain name

A domain name is a human-readable web address that points to an IP address and helps users to access websites or other resources in a convenient way. 

## IP address

An IP address (short for **Internet Protocol** address) is a label which is used to identify one or more devices on a computer network, such as the internet. It can be compared to a postal address. An IP address is a long number written in binary. 

Since such numbers are difficult to communicate, IP addresses are usually written as a set of numbers in a given order. Devices using IP addresses use the internet protocol to communicate. 

## TCP/IP

The TCP/IP model (Transmission Control Protocol/Internet Protocol) is a model with four layers which is for both modelling current Internet architecture, as well as providing a set a rules that govern all forms of transmission over a network. 

DARPA, an agency of the United States Department of Defense,created it in the 1970s. It evolved from ARPANET, which was an early wide area network and a predecessor of the Internet. The TCP/IP Model is sometimes called the Internet Model or less often the DoD Model.

---

## Production Ready

When we refer to an environment being production-ready we mean, that the server and the software you installed on it, runs, is backed-up, stable, maintainable and that it satisfies the needs for whatever you are doing on a regular basis. 

## Maintenance

The technical meaning of maintenance involves functional checks, servicing, repairing or replacing of necessary devices, equipment, machinery, building infrastructure, and supporting utilities in industrial, business, and residential installations.

Software maintenance in software engineering is the modification of a software product after delivery to correct faults, to improve performance or other attributes.

In a broader context maintenance can simply mean taking care of something, often over a prolonged period of time.
