# Setting up a Reverse Proxy
- swag (preconfigured set & forget) v nginx-proxy-manager (convenient web interface) ((recommended))
	- if only using linuxserver.io containers that have preconfigured swag configs, use swag, for a more general use case and having a webinterface use nginx-proxy-manager
[we get the quick config from here](https://nginxproxymanager.com/guide/#quick-setup)

```sh
$ mkdir /apps/reverse-proxy && touch /apps/reverse-proxy/docker-compose.yml
```

and edit the docker-compose with your favourite editor:

```sh
$ vim /apps/reverse-proxy/docker-compose.yml
```

and add:


```yml
version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

But we would like to change a few things to make our lives easier in the future:

```yml
version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - /apps/reverse-proxy/data:/data
      - /apps/reverse-proxy/letsencrypt:/etc/letsencrypt
    networks:
      - reverse-proxy
networks:
  reverse-proxy:
    external: yes
```

Here we added the paths for our app data. The reverse proxy doesnt use much space and needs to be fast so we make sure to use the fastest storage. (Remember, /apps is faster than /db which is faster than /data). In a large scale deployment we might want to use a faster database but for most use cases the standard sqlite database with this compose file is sufficient.
Now we can spin up our reverse proxy and access it in a web-browser:

Make sure we're in the folder 
```sh
# docker-compose up -d
```

And access it on 
[http://server-ip-address:81](http://server-ip-adddress:81)

Log in with the default Admin user credentials which you will be prompted to change.