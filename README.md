# Ghost + Nginx blog

A batteries-included blog platform running completely in Docker.

Uses [Ghost](https://ghost.org/) as the blogging platform, [Nginx](https://nginx.org/en/docs/j) reverse proxy, and MySQL 8 as the database backend.

This additionally improves on the base Ghost docker image by including:
- Complete database + proxy + blog setup with a single Docker Compose file
- Automatic Nginx configuration with [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy)
- Automatic SSL certificate generation using [docker-letsencrypt-nginx-proxy-companion](https://github..com/jwilder/docker-letsencrypt-nginx-proxy-companion) and LetsEncrypt
- Image storage backend with [Backblaze B2](https://www.backblaze.com/cloud-storage) or [Cloudflare R2](https://www.cloudflare.com/developer-platform/r2/)

## Prerequisites

- Docker - `v20+`
- Docker compose - `v2.17+`
- A domain name

## Installation

**1. Install Docker + Docker Compose**

Make sure you have a recent version of Docker installed, and Docker Compose.

Installation of these is beyond the scope of this project, but there are some [resources](#resources) below to get started.

**2. Clone the repository to your project directory**

Note: This repository has sub-repositories for the related storage engines.

```
git clone --recurse-submodules [REPO URL]
```


**3. Configure environment variables**

- Copy the configuration file from example.env to `.env`
- Change your configuration settings, including site name, email, site URL, and backend storage option.


**4. Build the Docker images**

- Pull the required Docker images: `docker-compose pull`
- Check your config is correct: `docker-compose config`

**5. Domain name and ports**

- Point your domain name to your server's IP address 
- Ensure your server has ports 80 and 443 open to allow HTTP traffic

## Usage

Clone the repo, configure it, and build the Docker images, as described above. 

Notes:
- Make sure you change your blog name and settings in `.env`.
- If you want to serve this to the public web, you'll need to open ports 80 and 443 on your server's firewall

Start the app:

```sh
docker-compose start
```

- Give it a couple minutes to run, initialize the database and generate the SSL certificates
- Watch the logs to ensure no errors in the SSL certs or database setup

It should now be running at your specified domain name. 


## Resources

**Ghost, Nginx, and Docker**

- Ghost - https://ghost.org/
- Docker - https://docker.com/
- Nginx - https://nginx.org/en/docs/

**Docker installation:**

- Installing Docker Compose - https://docs.docker.com/compose/install/
- Installing Docker Desktop - https://www.docker.com/products/docker-desktop/

**Nginx config:**

- Nginx configuration files - https://docs.nginx.com/nginx/admin-guide/basic-functionality/managing-configuration-files/

**Opening ports:**

- Opening ports on Linux - https://www.cyberciti.biz/faq/linux-iptables-firewall-open-port-80/



## Credits

- Inspiration for Nginx/Certbot Docker configuration - Gabriel Berthier - https://github.com/gabrielberthier/docker-compose-ghost-setup

## Maintainer
- 👋🏻 Matt Fields - [hello@mattfields.dev](mailto:hello@mattfields.dev)

## License

- MIT License
