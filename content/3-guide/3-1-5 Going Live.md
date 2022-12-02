# 3-1-5 Going Live

## 3-1-5a Connecting a domain
### Buying a domain
- We recommend Njalla.
	- ==Why do we do that==
	- ethics
		- Njal.la was founded by a group of freedom of information and privacy advocates who have been involved in various open projects since the start of the 2000s. Some of [them](https://en.wikipedia.org/wiki/Peter_Sunde), through their online activism, managed to attract the wrath of the Recording Industry Association of America which lead to both prison time and millions of euros in fines - fines which they will never be able to pay back as their hactivism was done for free and they never made a cent off it. This has effectively shut them out from society as a normal citizen and makes them rely on alternative economies to make a living. Njal.la is one of the projects that allows them to continue their privacy advocacy work and make a living from providing a convvenient service. They way Njal.la differs from a regular DNS provider in that they are the legal custodians of the domains you get through them, while they collect no information on you as a user. This means that should some government body demand information on the owner of a domain they would not be able to provide any information on you to them. Now, if you self-host from home, the DNS records will doxx you anyway. See [[2-5 Privacy considerations]] for ways to protect your home IP address from prying eyes. 
	- practicality
		- the main reason to use Njall however, isnt their past activism or their privacy shielding capabilities, no the main reason to use their services is the ease of use. Having used a handful of different DNS providers, we believe njalla has the simplest, easiest and most clear user experience.
	- downside: only crypto and paypal!
		- Bitcoin an d the environment
			- green crypto:
				- 
		- PayPal and its founders
			- Elon Musk
			- Peter Thiel
		- SWIFT and the international banking system: floating currencies as neo-colonial chains
			- maybe out of scope for this guide but let's jsut say there's no ethical consumption using FIAT either.
		- you can use something else as well
		- ==what else to use?==
			- [[3-1b-dns-providers-supported-ootb-npm]] 
#### If you use Njalla
- make a njalla account
- search what you want, pay for it

## 3-1-5b Connect your reverse proxy to your domain provider
- SWAG, not sure?
- Nginx-Proxy-Manager:
	- get njalla API
	- get wildcard ssl
		- *.domain.tld, domain.tld
	- use this cert for all containers using subdomains:
		- app.domain.tld
### 