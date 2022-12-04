# 2-3 System Considerations

- What is Linux and why are we using it?
- What are cool distributions
- Headless vs. GUI
	- what is a commandline?





- We recommend DietPi
	- community, super light weight, straight forward
	- while we recommend working with [[0-2_glossary_of_terms#Docker (software)|docker]] it comes with a lot of scripts for [[0-2_glossary_of_terms#On the Metal|on-the-metal]] installs
	- works for most [[0-2_glossary_of_terms#SBC (Single Board Computer)|SBCs]]
	- as well as old windows computers
	- we wrote [[3-1_installing_linux|guide]] for it
- There are many other systems that can make sense, depending on preference and situation
	- We recommend Alpine Linux
	- For advanced users. Since this manual is targeted at beginners to intermediates we don't include a guide for now
- Installing Linux on mac
	-



router access or something like zerotier?




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