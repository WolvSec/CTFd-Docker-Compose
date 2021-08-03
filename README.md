# CTFd-Docker-Compose
CTFd infra with Docker Compose

## Setup

### Docker
Make sure you have Docker and Docker Compose set up on your server.
### ENV
```bash
mv env.example .env
```
Then configure database details in `.env` with your preferred text editor

### Caddy (Reverse Proxy)
> Note: this can be replaced with `NGINX` or `Apache`, I'm using `Caddy` here just for convenience.

0. Make sure everything is working properly (use command in Launch part) with default configuration (You may need to point `ctfd.test` to your server in `hosts` on your local machine for testing)
1. Change `ctfd.test:80` in `Caddyfile` to the actual domain to be used, **Do not include port number** to allow HTTPS traffic

### Launch 🚀
```bash
docker-compose up -d
```

And you are all set 🎉! 
Allow a few minutes for Caddy to configure Let's Encrypt automatically, then your CTFd server should go live on the domain specified.