#### 1.3.2021, Lukas

setup: https://www.youtube.com/watch?v=fvnZlu5GgtI

how to start setting up odroid: https://wiki.odroid.com/odroid-h2/start

downloading ubuntu: https://releases.ubuntu.com/20.04/

step by step guide to create a bootabel linux usb drive: https://www.ubuntupit.com/how-to-create-a-linux-bootable-usb-flash-drive-tutorial/

downloading etcher, osx utility to make bootable linux usb drives: https://www.balena.io/etcher/

tried installing ubuntu from unix (is that the right term?) Got halfway through the install when it said that the CD is dirty or damaged (installing from a usb stick lol)

Booted into ubuntu, tried running installer from there, it crashed: ubi-partman failed with exit code 10. This seems to be a partitioning issue of the disk i want to install to? https://net2.com/how-to-solve-ubi-partman-failed-with-exit-code-10-in-ubuntu-18-04/

When trying again it almost worked, but crashed again. Also got stuck in boot a few times. Thinking this usb stick is faulty.

Flashing another USB stick now, and tying install from there.

System seems to boot fine from new USB stick, so i think that was the issue.

install went supeer smooth from the other usb stick. Minimal installation, web browser and basic utilities
user: `*******`
pw: `*******`

the computer is now set up. It's called **Cloudia**.

h2+ comes with 2.5g ethernet ports, which is very fast and a reason we bought it. But the chips are not recognized by ubuntu, have to install the drivers manually. more here (including how to): https://wiki.odroid.com/odroid-h2/hardware/install_ethernet_driver_on_h2plus

For this i reformatted the USB stick i originally used to flash ubuntu on, back to FAT, and downlaoded the drivers to there: https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-pci-express-software

But of course it's not over yet. I have to build the installer, for which i need to install a package called build-essential. But I don't have internet, so I have to find a way of doing it without. It's possible to use internet from a phone but i can't get it to work from an iphone. Something something apple walled garden lol.

There seems to be a way of doing this, but it might include installing ubuntu again. Will try this tomorrow: https://wiki.odroid.com/odroid-h2/application_note/install_ethernet_driver_on_h2plus

#### 2.3.2021, Lukas

Flashing a new USB, because I deleted it yesterday. Same procedure as always, formatting disk and using Etcher to flash Ubuntu. By using that image as the apt install repo, i can install build-essential which i can then use to compile the installer that I downloaded previously.

Of course, there was another small issue: the system date and time is set wrong, because there is no internet connection. Found a fix here: https://stackoverflow.com/questions/18235654/how-to-solve-error-clock-skew-detected

There are a few error messages when installing, but those are also in the manual. It seems to work fine, I am now connected to the internet. I tried finding out my ip, but net tools are not installed. When I tried installing with apt it's not working. Maybe because I set apt to be local in the previous steps? I unmounted the thumb drive and updated apt which seems to work. Now I could install net-tools. But it turns out I don't actually get my public IP address from that so it was not really necessary.

Went instead to https://whatismyipaddress.com/. Cloudia is online at: 81.204.58.114. Next up, SSH.

...

and it stopped working again. installing drivers again now, hopefully without building everything from scratch? This worked. I hope I don't have to do this every time I restart the server?

Anyway, I created an SSH account, following the guide from homebrewserver.club: https://homebrewserver.club/demystifying-ssh.html

user: `*******`
pw: `*******`

I ran into some issues on my client machine, where I had to update xcode. Then I need to check how to ssh a local machine since the homebrewserver example assumes that the ssh host already runs a webserver/domain. For this I found a handy guide: https://dev.to/zduey/how-to-set-up-an-ssh-server-on-a-home-computer

It works. I can connect to remote@cloudia at 192.168.2.85, so withing my local network. Now I have to see how to do this from outside this network. For this I will follow the same guide.

Setting up SSH from outside my network requires port forwarding. For this I had to log into my router, and make change some settings. In order to do this I had to reset the router to factory settings since I didn't know the password. Before doing so I wrote down the name and password of my wifi network, so that I could make a new one with identical settings, and all my devices would continue connecting to it automatically: https://www.kpn.com/service/internet/wifi-en-modems/herstart-reset-experia-box.htm

New login fo router:
user: `*******`
pw: `*******`

Port forwarding is specific to the individual router, so the guide I'm following is only giving general information for this. I found this guide to set up port forwarding on my specific router: https://openmyip.com/KPN-Experia-Box-router-setup

#### 3.3.2021, Lukas

The first step is reserving an IP address for cloudia. it was currently 192.168.2.85, so I left it at that. Cloudia will always have this IP on my locall network from now on. I did need to find another guide since the one from before was a bit too general. I found this on and managed to set up port forwarding in my home network: https://forum.kpn.com/internet-9/experiabox-v10a-poort-open-zetten-459268 I can from now on reach cloudia from anywhere.

I'm now generating SSH keys, following the guide from before. This image has been generated as a scurity measure:

```
+--[ED25519 256]--+
|           .+oo.+|
|           .o. o.|
|           . o   |
|       .. . o.+ .|
|      ..S= =+o * |
|       **********|
|      o+.....+ o |
|     o++ o=o. .  |
|     .*+++o+o    |
+----[SHA256]-----+
```

I had to set up a passphrase, as usual it's CloutS3rvice! While setting up the SSH, I got an error message though, something about my user not being part of the sudoers list. Thiss guide says I have to fix this in unix, but i willl try something else first: https://www.tecmint.com/fix-user-is-not-in-the-sudoers-file-the-incident-will-be-reported-ubuntu/

It works when logging in with the pleb account, and then switch users (giving sudo rights to remote I think). When adding the PubkeyAuthenticate to the file I had to find how to edit a file first: https://www.lostsaloon.com/technology/how-to-append-text-to-a-file-in-linux/

I also had to change permissions for the folder, so I could edit the config file: https://www.linux.com/training-tutorials/how-manage-file-and-folder-permissions-linux/

I didn't manage to add he pubkey line over commandline so I just did it over the GUI.

I also had to change some more permissions, kinda scary lol. This thread said to set them to 600: https://stackoverflow.com/questions/9270734/ssh-permissions-are-too-open-error

It works!! I can now login from anywhere with ssh cloudia

#### 3.3.2021, Lukas (continued)

Trying to log in from another network now, it didn't work anymore. I first thought it was broken, but it's because I still had it set up to the internal IP address. Fixing this in the config file works though! After adding this IP address to my known hosts, it works! Cloudia is reachable from the rest of the world.

However, we would like to get around the fact that we are always hidden behind the router—after all we would like to be a nomadic server. For this I have started reading about IP4, IP6, NAT and Source Routing: https://security.stackexchange.com/questions/44065/with-ipv6-do-we-need-to-use-nat-any-more#130321

There is also something called Dynamic DNS, but i'm not completely sure what it is yet. https://www.lifewire.com/definition-of-dynamic-dns-816294 One service in germany does it for free? https://ydns.io/

#### 10.3.2021, Lukas

We bought a URL today: 192168285.xyz. It's cloudia's internal IP address, and the cheapest domain we could find. I bought it on namecheap and forwarded it to cloudia's public IP address.

I then forwarded ports 80 and 443 to cloudia on our router, which are http and https requests, respectively.

I'm now following the directions at https://homebrewserver.club/fundamentals-webserver-website.html to set up a basic webserver. They suggest apache, so I went with that as well (as opposed to Nginx.

This involved learning how to edit files (the apache config file for example) in the terminal, since cloudia no longer has a gui, and i'm doing everything remotely. https://linuxize.com/post/how-to-use-nano-text-editor/

In order to install Certbot, which provides https services, I needed to check some ubuntu specific install commands: https://certbot.eff.org/instructions In this guide it gives an option to just turn certbot on by default, but I will do it manually for my apache configuration so maybe i learn something....

I did learn something I think, because I got some error messages and had to understand them. I forgot to edit some of the placeholder text in the apache config file. But: it's working, we are self hosting now at https://192168285.xzy!

I now wanted to automatically redirect to https, so i followed the example in this post: https://stackoverflow.com/questions/16200501/how-to-automatically-redirect-http-to-https-on-apache-servers, which was basically just adding a few lines of code to the http part of the apache config file, and enabling an apache module

I've also already started trying to set up a subdomain. I followed this guide for it: https://www.youtube.com/watch?v=uxMxJPuuIzs. Basically I had to make an entry with namecheap, where I bought the domain, and set up a new config file in apache, and link a server to a directory. pretty easy. i had to make sure to remove the https part from the setup, then do the certbot thing, and then edit the apache config again.

It is, however, not working, and i don't know why. I can ping cloud.192168285.xyz and i get a response? but nothing shows up when i try to load the page.

Update: it works. it takes a while for the subdomain to be registered with namecheap.

I am now trying to install nextcloud. I am following the guide in the official nextcloud doc: https://docs.nextcloud.com/server/21/admin_manual/installation/source_installation.html#installation-via-install-script

When trying to download the script with wget, i get a html page instead (the actual github page). so I checked online and found that you can get the actual file by changing the link slightly which will redirect you to the actual file: https://unix.stackexchange.com/questions/228412/how-to-wget-a-github-file

I ran the script and it's crazy, there is a GUI in my terminal lol:

But there are also errors. It says apache2 detected must be clean server. A quick google search says i will have to remove apache, because nextcloud installs it's own version of apache. I will probably have to spend more time on this.

#### 16.3.2021, Lukas

Trying the Netxcloud installer again, and following the steps, with the same error message of course. I made a new user for this, ncadmin with all permissions.

user: `*******`
pw: `*******`

so first i deinstall apache. Bit sad but ok. https://linuxconfig.org/how-to-remove-apache-web-server-from-ubuntu

now trying to run the script again. It says to remove mysql common. https://www.cyberciti.biz/faq/uninstall-mysql-ubuntu-linux-command/

Also switching users now to the one i created before: https://linuxhandbook.com/change-user-command-line/

Stuff is happening for sure now. Let's see. There is an error message about not having a second drive connected to the server. We need to go shopping.

It also asked me to chose a DNS provider. For now I selected cloudflare, but I guess it's possible to do this yourself? I don't know exactly what this means.

The script works great though, it also made a database I believe? PostgreSQL password: `*******`

For now I opted to install all nextcloud packages. There was an error message that issuetemplate couldn't be installed because of compatibility issues, but that it's whatever. Then the installer restarted cloudia, and now i lost connection with her. Cloudia also doesn't show up in the list of connected devices when logging into my router. I will wait a bit and see if she shows up later, maybe there is some more setup things going on that i can't see now? Otherwise I will do a hard restart i guess... The lights are blinking, but she is not showing up on the network...

Ok so it seems that the ehernet drivers once again uninstalled themselves on restart. I assume this has to do with very annoying. Had to connect my screen again, and install locally. Now will log in over ssh again and see if i can finish the install. It did! The installer started again and I am being guided through it.

This install is very complicated. I think i fucked it up lol by cancelling it accidentally. I think I need to start from scratch.

Update: now I really fucked it up. I deinstalled apache and the database to start a new install. Then I signed into the ncadmin user, and the second half of the install script started again, but nothing is working. I need to find a better tutorial. And maybe set up linux from scratch.

Ok so I followed a different guide, and used snap to install nextcloud. I don't think it's really the way to go, but for now it's cool: https://www.youtube.com/watch?v=g1mYxrxdJXM. It also really works. Lol. So much struggle before. Let's see if I can set up https and a domain etc.

Ok he just explained it later in the video this was so easy. Cloudia now has a nextcloud instance running at https://192168285.xyz

Next: I would like to have nextcloud running in a subdomain, and the main domain for a webserver. Also we should get proper hard drive(s), and do a nextcloud installation from scratch, not in this snap image and with raid system. But for now: cool!

#### 12.04. Lukas

starting from scratch. Will try to install Ubuntu Server this time, no GUI at all. Downloaded from here, flashing a USB stick now: https://ubuntu.com/download/server

After some initial trouble with USB sticks, I am now following the Ubuntu Server Installer. I am using this guide (for partitioning etc): https://www.tecmint.com/install-ubuntu-20-04-server/

user: `*******`
server: `*******`
pw: `*******`

This time I am equiped with my install USB and another one for transport. However Ubuntu Server doesn't automount usb sticks, so i have to do this by hand: https://help.ubuntu.com/community/Mount/USB

Setting the apt to the ubuntu server installer didn't work though. Trying now to make a new usb stick with ubuntu desktop and flashing from there. It's very slow because all my USB sticks suck. I did manage to copy the drivers to the server with the other stick that I had so once I manage to install the build essentials package I can install the drivers.

But it didn't work. Some packages didn't install. Fuck it. Installing Ubuntu 20.04 Desktop now, because that worked last time. Too bad, since the server should be faster... Next time

So, new minimal install of Ubuntu Desktop. Same user/pw as above. Install went fine. So did the build essential install. And installing the ethernet drivers. Even after a restart. I am now moving the server over to the internet. Whatever.

Connected cloudio to the internet, running headless now. I assigned a new internal static IP to cloudio (since I changed the name). I mapped the same IP since we already have that URL bought and then I don't have to change the port forwarding. But of course I forgot to set up ssh. So I need to move my screen to cloudio now (i was really hoping i did't have to do that). Following homebrewserver again: https://homebrewserver.club/demystifying-ssh.html#validating-server-host-keys

Following this tutorial now for setting up raid: https://www.tecmint.com/create-raid1-in-linux/ it was very easy :-D

Now trying nextcloud. For this I am following the guide on https://docs.nextcloud.com/server/20/admin_manual/installation/source_installation.html#installation-via-install-script as before

I downloaded the script and am running it over the terminal. I will make sure to create a new user and not uninstall anything in between haha.

I made a new user:
`*******`
`*******`

At some point the script was asking me where to put the "data" folder. It didn't let me select my raid configuration. I think I now have nextcloud installed on only one drive.

When asking about DNS provider, I said local. Let's see lol.

I also get an error message from ssh. I think I will have to set this again?

I just said yes to all suggested packages to be enabled.

something went wrong. I had to stop the install. Now it doesn't install anymore. I will wipe it again, install ubuntu from scratch. Ugh. I will then try a different install method, not the script. There is another method outlined here: https://docs.nextcloud.com/server/21/admin_manual/installation/example_ubuntu.html

Wiped thee system, reinstalled, installed the ethernet drivers and ssh, as usual lol, set up raid system again because i formatted one of the disks by accident before. If i had a backup disk this would be a great moment to make a backup. But I don't lol.

Following the official nextcloud guides has been working well. After the install I followed the regular linux install guides from nextcloud. https://docs.nextcloud.com/server/21/admin_manual/installation/source_installation.html#apache-web-server-configuration

I have the installer working in the browser! I did not understand the part about pretty URLs but it's not important. I also still have to turn on https, but i think i can do that myself with letsencrypt or something like that. i also don't know where my database is. and i have to give rights to the data folder for nextcloud.

After one error message I found this: https://help.nextcloud.com/t/cant-create-or-write-into-the-data-directory/10184

I had to adapt the user for apache i believe, similar to what i did in a prev step of the install (chown www-data etc).

**IT WORKS! WITH THE DATA ON THE RAID DRIVES.**

for https i'm following good old homebrewserverclub: https://homebrewserver.club/fundamentals-webserver-website.html

i'm checking now if I can install focalboard. https://www.focalboard.com/download/personal-edition/ubuntu/

Focalboard assumes a different database and a different server (nginx and Postgresql), but i feel on top of things today lol. Let's see...

the database stuff was over my head, but i haven't broken the nextcloud instance so far so that is good. I did make a new database in mariadb but i guess it's fine. I will just install postgresql and let them run next to each other.

It's not working (of course lol), but it can actually just be the config in the apache server, cause i left out a bunch of stuff. Need to find how to translate the config file from nginx to apache.

i gave up, and tried uninstalling everything i installed for focalboard. Nextcloud still works tho :)​
