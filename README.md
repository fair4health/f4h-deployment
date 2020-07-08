# f4h-deployment

# Context



Finally https is provided by means of an [nginx reverse proxy]().

# Description

The repository provides the docker compose scripts to provide the FAIR4Health platformm ready for production. It provides https through nginx as reverse proxy and authentication by means of KeyCloak IdM and Proxy.
The software is prepared for production with the following architecture (letsencrypt for https):

<p align="center">
	<img src="img/f4h-architecture.jpg">
</p>

Nginx is used as reverse proxy. For testing, port 80 and simple names are used: f4h-portal, f4h-backend, keycloak, discovery, ppddm-manager. For production the port must be changed to 443, and letsencrypt must be used to provide the https certs. You should change the suitable domains and configuration details in the .env file and uncomment docker-compose.yml code before deploying the containers.

# Technologies and tools

- Docker compose
- KeyCloak IdM
- MariaDB
- Nginx as reverse proxy and letsencrypt

# How to deploy

[Install Docker CE](https://docs.docker.com/install/). For Windows and Mac a [docker toolbox desktop is available](https://docs.docker.com/toolbox/overview/). Remember that Docker toolbox is published at 192.168.100.99 (`user: docker, password: tcuser`)

**Tip**: To avoid performance issues, increment VirtualBox default VM memmory to 4g

Deploy using docker-compose:

```
Stop and remove the containers
docker-compose down

Launch the containers (dettached)
docker-compose up -d
```

**IDENTIFIED ERRORS**

- 

# How to use

[Environments](https://docs.docker.com/compose/environment-variables/) are used to configure the installation. Modify the `.env` to comply your needs.

To access the portal:
```
```

The nginx reverse proxy allows also accessing using domains: monitor, portainer and keycloak (if you redirect the domains to localhost or the IP where you are deploying the containers).

**Tip**: if you are using Docker toolbox point the domains to IP 192.168.99.100.

```
192.168.99.100 keycloak
```

# How to contribute

Features and bug fixes are more than welcome. They must be linked to an issue, so the first step before contributing is the creation of a [GitHub issue](https://github.com/fair4health/f4h-deployment/issues).

# External resources

- 

# License

Apache 2.0.

