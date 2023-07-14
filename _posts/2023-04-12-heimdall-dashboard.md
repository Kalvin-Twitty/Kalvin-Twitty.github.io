---
layout: post
title: "Meet Heimdall, Your Homelab Application Dashboard123"
date: 2023-04-12 02:00:00 -0500
categories: self-hosted
tags: homelab heimdall self-hosted truenas-scale docker
---

# Installing Heimdall Dashboard using Docker

Heimdall is an open-source dashboard that allows you to monitor and manage multiple applications in a single place. It's easy to install and configure, and can be deployed using Docker.

To install Heimdall using Docker, follow these steps:

## Step 1: Install Docker

If you don't already have Docker installed on your system, you'll need to install it first. Docker provides a simple way to package and run applications in containers, which makes it easy to deploy Heimdall.

To install Docker, follow the instructions for your operating system on the [Docker website](https://www.docker.com/get-started).

## Step 2: Create a Docker Compose file

To run Heimdall using Docker, you'll need to create a Docker Compose file. This file defines the services that make up your application, including the Heimdall service.

Create a new file called `docker-compose.yml` and add the following content:

```yml
version: '3'
services:
heimdall:
image: linuxserver/heimdall
container_name: heimdall
ports:
- '80:80'
environment:
- PUID=<UID>
- PGID=<GID>
- TZ=<timezone>
volumes:
- '/path/to/heimdall/config:/config'
- '/path/to/heimdall/data:/data'
```

In this file, replace `<UID>` and `<GID>` with the user ID and group ID that you want to use for the Heimdall container. You can find these values by running the `id` command in your terminal. Also, replace `<timezone>` with your timezone.

Finally, replace `/path/to/heimdall/config` and `/path/to/heimdall/data` with the paths to the directories where you want to store Heimdall's configuration and data.

## Step 3: Start the Heimdall container

Once you've created the Docker Compose file, you can start the Heimdall container by running the following command in your terminal:

```bash
docker-compose up -d
```


This command will start the Heimdall container in detached mode, which means it will run in the background. You can then access the Heimdall dashboard by opening a web browser and navigating to `http://localhost`.

## Step 4: Set up an A record in your DNS settings

After you have installed and configured the Heimdall dashboard service on your server using Docker, you may want to access it using a custom domain name instead of the IP address or localhost. To do this, you can create an A record in your DNS settings that points to the IP address of your server.

To set up an A record for your Heimdall dashboard, follow these steps:

1. Log in to your domain registrar or DNS provider's website and navigate to the DNS settings for your domain.

2. Create a new A record with a subdomain of your choice (e.g. `heimdall.yourdomain.com`) and set the IP address to the public IP address of your server where the Heimdall dashboard is running.

3. Save the changes to your DNS settings.

4. Wait for the DNS changes to propagate, which can take anywhere from a few minutes to several hours depending on your DNS provider.

Once the DNS changes have propagated, you should be able to access your Heimdall dashboard using the custom domain name you set up in the A record. Simply open a web browser and navigate to `http://heimdall.yourdomain.com` (
