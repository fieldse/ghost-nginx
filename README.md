# Ghost + Nginx blog

A simple blog platform, batteries included, running in Docker containers with [Ghost](https://ghost.org/) as the blogging platform, [Nginx](https://nginx.org/en/docs/j) reverse proxy, and MySQL 8 as the database backend.

## Prerequisites

- Docker - `v20+`
- Docker compose - `v2.17+`

## Installation

Make sure you have a recent version of Docker installed, and Docker Compose.

Installation of these is beyond the scope of this project, but there are some [resources](#resources) below to get started.

1. Clone the repository to your project directory
2. Change your configuration settings (see `.env`)
3. Install and build the required Docker images: `docker-compose build`

## Usage

Install and build the Docker images, as described above. Make sure you change your blog name and settings in `.env`.

Start the app:

```sh
docker-compose start
```

It should now be running on port `80` internally.

If you want to serve this to the public web, you'll need to open the port on your webserver.

## Resources

- Ghost - https://ghost.org/
- Docker - https://docker.com/
- Nginx - https://nginx.org/en/docs/

**Installation guides:**

- Installing Docker Compose - https://docs.docker.com/compose/install/
- Installing Docker Desktop - https://www.docker.com/products/docker-desktop/

**Server configuration**

- Opening port 80 on Linux - https://www.cyberciti.biz/faq/linux-iptables-firewall-open-port-80/

**Nginx configuration**

- _TODO_


## Credits

Nginx/Certbot Docker configuration
- Gabriel Berthier - https://github.com/gabrielberthier/docker-compose-ghost-setup


## License

- MIT License
