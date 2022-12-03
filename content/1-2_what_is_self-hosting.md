# 1-2 What is self-hosting

At this point, it's probably good to explain what a [[0-2_glossary_of_terms#Server|server]] is in a few words: A server is a computer that *serves* information to a user (or *client*) machine. It's an essential part of everything *online*—arguably, the internet is just a bunch of servers.

When you visit a website, somewhere in the world there is a computer that has the website stored on it—that computer is one example of what we call a server. When you enter a URL into your browser, you are being connected to this server, and it will send you back (*serve* you) the content of the website. Your computer then displays this website in your browser, similar to the way a TV receives the signal from the TV station and renders it into an image on the screen.

Similarly, if you edit a Google Docs file together with someone else, somewhere in the world there is a server on which the content of this document is stored. Every time you make a change in the document, this change is sent to the server, which then passes on (*serves*) the changes you just made to all the other users, in real time. This way everyone is always in sync and can see what the other people are writing, in real time.

Obviously, on a practical level things are a bit more complicated than that but when people say *the cloud is just someone else's computer*, this is what they mean: the so-called cloud is just a bunch of servers that store everyone's data and keep everyone connected. In the case of big tech, these servers are part of huge data centers, incredibly complex operations that exist in sepcially designed buildings that use the energy equivalent of small cities. This scale is "necessary" because they serve millions of people simultaneously, all over the world, all of whom expect things to happen immediately and without a moment of delay or a second of downtime.

Self hosting is the opposite of that. Instead of having all your data on someone else's computer, as is the case with the cloud, it's setting up your own computer to do the same thing. At least theoretically, any computer can function as a server and while it requires some technical know-how, time and effort, it's possible to set up a small server in your own home or work place that can replace some or all of the cloud services you (and your colleagues?) use. Since you most likely don't need to serve millions of people at the same time, the hardware, software and energy requirements for this can be surprisingly low. If you want to supply file sharing, collaborative writing, video calling and a shared calendar for yourself and the people in your surroundings (let's assume this is up to 15 or 20 people), chances are that an old laptop that you or someone you have lying around would be up to the task.

## 1-2-1 What are the benefits of self-hosting?

As previously mentioned, self-hosting comes with a set of ethical and practical advantages:

- it allows people to gain (more) control over their data, both in terms of privacy and access to their files
- it allows them to become more self-sufficient in their digital infrastructure,
- it lets them build systems that can adapt and develop along with their needs while simultaneously enabling them to plan for longevity,
- it often allows them to build systems that are more closely adapted to their specific needs,
- in the process, users will learn a lot about the way digital infrastructures work, making them more adapt at avoiding mistakes and fixing problems in the future,
- It allows users to minimize their ecological footprint through lower energy usage and the recycling of old hardware,
- It makes them less dependent on companies that are [[1-1_problems_with_the_cloud#1-1-2 Why is that a problem?|diametrically opposed to their ethical values]]

## 1-2-2 What are the challenges of self-hosting?

But nothing is perfect and life is not fair, and like everything else, self-hosting comes at a cost. The trade-off here is mostly about the time and energy that an individual or group has to spend on it (more on this in our [[1-1_problems_with_the_cloud#1-1-3 Some notes on expense|notes on expense]]).

- Self-hosting means maintenance. Software has to be updated, hardware has to be upgraded or exchanged, issues need to be solves every once in a while. This is a commitment that you need to be aware of before deciding to self-host (parts of) your digital infrastructure.
- While most things we describe here are really not rocket science, self-hosting always comes with a certain risk of just *fucking up*—of breaking something, accidentally deleting data, or of hardware failure. While there are [[2-4_sofware_considerations#2-4-2 The *3-2-1* Backup Rule|ways to prevent irreversable damage]], it's good practice to consider the consequences of an interruption of service before deciding to switch to self-hosting for a particular service.
- While it's possible to reduce your ecological footprint through practices like self-hosting (where you can use computers that are extremely energy efficient and/or reuse old hardware), there are limits, and from a radical ecological point of view, computing is not ecologically sustainable per definition. The materials that go into the production of chipsets are extracted at considerable costs to the environment, and the amount of energy that goes into the production of a modern computer cannot never be compensated for, no matter how energy efficient it is. This is not even accounting for the fact that eventually it will probably end up in a landfill somewhere.

## 1-2-3 List of things that can be replaced by self-hosting

==Need to write this list!==