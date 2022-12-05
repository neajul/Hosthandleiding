# Awesome List, awesome software

## Backups

- [https://docs.linuxserver.io/images/docker-duplicati](https://docs.linuxserver.io/images/docker-duplicati)
	- Great backup solution that works with basically every protocol and most cloud services
- [https://docs.linuxserver.io/images/docker-syncthing](https://docs.linuxserver.io/images/docker-syncthing)
	- super simple folder/file sync
		- Can be used as a backup solution for simple server setups
	- If you don't need a full cloud service but rather just share folders between a bunch of users this is the go to
	- based on similar technology to torrents, you just go to the local web interface and add folders that you want to sync between devices
	- having a server attached to syncthing means that you will always sync folders even if your other devices or collaborators are not online at the time you make changes, but, it also works without a server to just connect devices to eachother

## Markdown editors

- [https://docs.linuxserver.io/images/docker-hedgedoc](https://docs.linuxserver.io/images/docker-hedgedoc)
	- collaborative
	- probably this is the best one for just doing that
- [https://docs.linuxserver.io/images/docker-nextcloud](https://docs.linuxserver.io/images/docker-nextcloud)
	- collaborative
	- the standard text editor in nextcloud is a markdown editor
- [https://docs.linuxserver.io/images/docker-raneto](https://docs.linuxserver.io/images/docker-raneto)
	- a knowledgebase / wiki things using markdown files
	- it has an editor build into it as well
- [https://docs.linuxserver.io/images/docker-dillinger](https://docs.linuxserver.io/images/docker-dillinger)
	- not collaborative
	- saved in browser cache, this means that nothing is stored on the server
	- you can connect cloud services to it to import files and export as html or just write in the browser
	- useful for having a simple clean thing that you can always quickly access and work in in your browser
	- https://dillinger.ada.gallery if you wanna try it q:

## File sharing

- [https://docs.linuxserver.io/images/docker-xbackbone](https://docs.linuxserver.io/images/docker-xbackbone)
	- super simple multiuser file browser basically
- [https://docs.linuxserver.io/images/docker-nextcloud](https://docs.linuxserver.io/images/docker-nextcloud)
	- full fledged Google Drive/Docs replacement
	- This is what everything from your nerdy aunty to the French/German/Swedish governments are using to replace American cloud services
	- fully customizable white label, meaning you can put your own logo on it and add as many different addons to it as you want to add various functions to it
	- can be an all in one thing so that you literally don't install any other cloud services than this
		- This is good cause it's only one thing to manage but it can quickly become tricky to make sure all the different addons you add still work with an update to nextcloud
		- the system requirements when you add a lot of different addons can become quite heavy
	- A large part of it is written in PHP so with large user bases the type of server/infrastructure you need can become pretty beefy
	- Professional support from Nextcloud is behind paywall but there are forums and telegram chats to utilize if you have more time than money
- [https://docs.linuxserver.io/images/docker-syncthing](https://docs.linuxserver.io/images/docker-syncthing)
	- super simple folder/file sync
	- If you don't need a full cloud service but rather just share folders between a bunch of users this is the go to
	- based on similar technology to torrents, you just go to the local web interface and add folders that you want to sync between devices
	- having a server attached to syncthing means that you will always sync folders even if your other devices or collaborators are not online at the time you make changes, but, it also works without a server to just connect devices to eachother
- [https://docs.linuxserver.io/images/docker-snapdrop](https://docs.linuxserver.io/images/docker-snapdrop)
	- simple local network file sharing, inspired by Apple Airdrop
	- also works over Virtual Private Networks so can be interesting for simple file sharing between users
- [https://docs.linuxserver.io/images/docker-pydio-cells](https://docs.linuxserver.io/images/docker-pydio-cells)
	- full fledged Google Drive/Docs replacement
	- Written in Go, so scales nicely with more users while still not requiring too beefy hardware
	- The white label features are behind a Pay wall along with some of the more niche use cases
- [https://docs.linuxserver.io/images/docker-projectsend](https://docs.linuxserver.io/images/docker-projectsend)
	- Simple WeTransfer replacement
	- Still quite simple in its functions
	- Can be tricky to set it up behind a reverse-proxy while allowing for large files to be sent
- Honorable mention: IPFS 
	- IPFS, *Interplanetary File System*, is a protocol for distributed serverless environments.
	- Wikileaks most likely uses something like this to sync their various servers
	- there are cloud based setups that can use IPFS as a backend, one that looks promising is [Iroh](https://iroh.computer), however we dont have enough experience with it to recommend in this version of the manual