---
layout: post
title: "Hosting Your Own Website with Apache HTTP Server"
date: 2023-01-02 02:51:00 -500
categories: coding
tags: windows coding javascript wsl node windows linux ubuntu
image:
  path: /assets/2023-01-02-hosting-apache/apache.png
---

# Hosting Your Own Website with Apache HTTP Server

In this guide, we'll walk through the process of deploying a web server using Apache HTTP Server and hosting your own website.

## Prerequisites

Before we begin, ensure you have the following:

- A server or virtual machine running a Unix-like operating system (e.g., Linux)
- Access to the command line interface with administrative privileges
- Basic understanding of terminal commands and file manipulation

## Step 1: Installing Apache HTTP Server

1. Update the package index:

    ```bash
    sudo apt update
    ```

2. Install Apache HTTP Server:

    ```bash
    sudo apt install apache2
    ```

3. Start the Apache service:

    ```bash
    sudo systemctl start apache2
    ```

4. Verify that Apache is running by navigating to `http://your_server_ip` in your web browser. You should see the default Apache landing page.

## Step 2: Configuring Your Website

1. Navigate to Apache's configuration directory:

    ```bash
    cd /etc/apache2/sites-available
    ```

2. Create a new configuration file for your website:

    ```bash
    sudo nano your_website.conf
    ```

3. Add the following configuration to the file, replacing `your_domain_or_ip` with your actual domain name or IP address and `your_website_directory` with the path to your website's files:

    ```apache
    <VirtualHost *:80>
        ServerAdmin webmaster@localhost
        ServerName your_domain_or_ip
        DocumentRoot /var/www/your_website_directory

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>
    ```

4. Save and close the file (`Ctrl + X`, then `Y` to confirm).

5. Enable your website configuration:

    ```bash
    sudo a2ensite your_website.conf
    ```

6. Reload Apache to apply the changes:

    ```bash
    sudo systemctl reload apache2
    ```

## Step 3: Uploading Your Website Files

1. Transfer your website files to the server using SCP, FTP, or any other preferred method.

2. Place your files in the directory specified in your Apache configuration (`/var/www/your_website_directory`).

## Step 4: Making Changes

1. To make changes to your website, edit the files in your website directory (`/var/www/your_website_directory`).

2. After making changes, reload Apache to apply them:

    ```bash
    sudo systemctl reload apache2
    ```

3. Test your website to ensure the changes have been applied.

Congratulations! You've successfully deployed a web server using Apache HTTP Server and hosted your own website.
