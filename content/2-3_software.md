# Software

> Don't argue, use docker

When using a consumer PC, installing software has become so easy we barely notice it. You either open an installer and click yes—yes—yes until the installation is complete (without reading the Terms and Conditions, of course), or you simply drag an icon into another icon, or you just click `install`.

But under the hood what is happening is a bit more complicated than that, and as ==sysadmins that's where we operate: under the hood.== This is where docker comes in and make our lives better. But let's start by explaining what exactly the problem is that docker solves.

## 3.1 The problem: dependencies

When writing software, you try not to reinvent the wheel. Instead, you *depend* on things that other people have written before you—a programming language maybe, a database, an image library. *Dependencies* are a sysadmins nightmare, especially when trying to run multiple services simulataneously.

For example: a file server might run on PHP. This usually means that it requires a specific version of PHP, a programming language that gets updated continuously. But this file server is also supposed to have a web interface—a website where users can look at their files. This requires a web server to be installed. The sysadmin of this server now wants to install a second service on the same server, a note-taking app. This note-taking app might also require PHP, but a different version, so there is a conflict here. On top of that, it also requires a web server, so that users can edit their notes in the browser, but this specific app needs a different type of web server. So there is another conflict here!

## 3.2 The solution: containers

The more things you want to run in parallel, the more you will run into things like this. That's where containers come in.

**Containers**, as the term suggests, “contain” every little thing that an application may need to be executed. It's like a transportable box, filled with tools and libraries and settings and all that other good stuff that we need to run the application. Docker, which we strongly recommend, is a container platform. In the example above, when using docker, both the file server and the note-taking app would come in containers, packed up together with their own PHP versions and web servers, and without the risk of interference. In fact, it becomes so easy, you don't even have to know what dependencies the things you install actually need.

## 3.3 I'm sold, where do I find containers?

A good place to start looking for docker containers is the website [linuxserver.io](https://docs.linuxserver.io/general/awesome-lsio), though if you have an application you would like to run in mind, you can probably simply search it up online by adding "docker" to your query.