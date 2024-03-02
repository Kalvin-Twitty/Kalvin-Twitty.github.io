---
title: Building, Deploying, and Hosting a Static Web Page with Jekyll
date: 2024-03-01 01:00:00 -500
categories: [homelab, hardware, software, website]
tags: [homelab,websites,jekyll,software,]
image:
  path: /assets/2024-03-01-jekyll-static-webpages/jekyll_pages.jpg
---
# Building, Deploying, and Hosting a Static Web Page with Jekyll

In this guide, we'll walk through the process of building, deploying, and hosting a static web page using Jekyll, a static site generator.

## What is Jekyll?

Jekyll is a simple, blog-aware, static site generator built in Ruby. It allows you to create static websites from plain text files using templates. Jekyll is particularly popular for building personal blogs and portfolios.

## Prerequisites

Before we begin, ensure you have the following installed:

- Ruby and RubyGems
- Bundler (a Ruby dependency manager)

## Step 1: Installation

1. Install Jekyll using RubyGems:

    ```bash
    gem install jekyll bundler
    ```

## Step 2: Creating a New Jekyll Site

1. Create a new Jekyll site:

    ```bash
    jekyll new my-site
    ```

2. Change into the newly created directory:

    ```bash
    cd my-site
    ```

## Step 3: Running the Development Server

1. Start the development server:

    ```bash
    bundle exec jekyll serve
    ```

2. Access the site in your web browser at `http://localhost:4000`.

## Step 4: Customizing Your Site

1. Edit the `_config.yml` file to customize settings such as site title, description, and theme.

2. Modify the Markdown files in the `_posts` directory to add your content.

3. Customize the layout and styling of your site by editing HTML and CSS files in the `_layouts` and `_sass` directories.

## Step 5: Building Your Site

1. Build your site for production:

    ```bash
    bundle exec jekyll build
    ```

2. The generated static files will be placed in the `_site` directory.

## Step 6: Deploying and Hosting Your Site

1. Choose a hosting provider for your static site. Options include GitHub Pages, Netlify, and AWS S3.

2. Follow the hosting provider's instructions to deploy your site. Typically, this involves pushing your code to a Git repository and configuring your hosting provider to serve the static files from the `_site` directory.

### Example: Deploying to GitHub Pages

1. Create a new Git repository on GitHub.

2. Push your Jekyll site to the repository:

    ```bash
    git remote add origin https://github.com/username/repo-name.git
    git push -u origin master
    ```

3. Enable GitHub Pages for the repository in the repository settings.

4. Your site will be available at `https://username.github.io/repo-name`.

Congratulations! You've built, deployed, and hosted your own static web page using Jekyll.
