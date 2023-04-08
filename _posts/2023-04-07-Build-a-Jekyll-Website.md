---
layout: post
title: How to deploy a Jekyll Website Using Github Pages
date: 2023-04-07 08:30:00 -0500
categories: self-hosted
tags: jekyll website github gitlab
---

# How to deploy a Jekyll Website Using Github Pages.

 Jekyll is a static site generator that transforms your plain text into beautiful static web sites and blogs. It can be use for a documentation site, a blog, an event site, or really any web site you like. It’s fast, secure, easy, and open source. I'll be using techno-tims repo/the chirpy theme. 

 Some useful links-
 
 [Techno-Tim's Video](https://www.youtube.com/watch?v=F8iOU1ci19Q)

 This is a link to technotims video

He does an excellent job walking you through the steps.

## Prerequisite

* A GitHub account Make sure you have one before hand. 
* A linux Machine or you can use GitHub Workspaces inside VS Code.

## Getting Started
Before getting into everything you'll need to update and install some dependencies.

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev git
```

This checks your machine for updates then you use `apt install` to `install` ruby the language in which jekyll is built on.


To avoid installing RubyGems packages as the root user:

```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Install Jekyll `bundler`

```bash
gem install jekyll bundler
```

### Creating the Site based on Chirpy Starter
Before your able to clone your repositories you'll need to enable ssh on your github account simply

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
#enter your email
```
This will generate the keys for you both public and private

it will ask you where you want to save the file at just press enter

then it should prompt you for a password if you dont want to set a password just press enter twice

```bash
eval "$(ssh-agent -s)"
> Agent pid 420
```

this starts the ssh agent then all you need to do is add that file 

```bash
ssh-add ~/.ssh/id_ed25519
```

aftet that you just need to cat the file out copy and paste it into your GitHub account ssh key section in your settings

```bash
cat ~/.ssh/id_ed25519.pub
```


Go ahead you can clone my repo or go right to the chripy-starter repo on GitHub

When you clone the repo make sure you name it "your-github-username-".github.io

![Alt text](/assets/2023-04-07-Build-a-Jekyll-Website%20IMG/Cloning%20Repo.png)

Links to both:

[Starter Repo from Chirpy](https://github.com/cotes2020/chirpy-starter)

[My repo](https://github.com/Kalvin-Twitty/Kalvin-Twitty.github.io)

So to see what your site looks like without any configs to the `_config.yml`

you can simple do

```bash
bundle exec jekyll s
```

This will serve your site from your local machine on port 3000

some things they don't tell you that are important for you to know as your going

the most important file that you need to edit is the `_config.yml` this file has base line information that is used to build your site.


it is well documented with comments but don't use `Capital Letters` inside the URL section Jekyll and github don't like that

ensure you line up all sections properly like this

```yaml
social:
  # Change to your full name.
  # It will be displayed as the default author of the posts and the copyright owner in the Footer
  name: your_full_name
  email: example@domain.com # change to your email address
  links:
    # The first element serves as the copyright owner's link
    - https://twitter.com/username # change to your twitter homepage
    - https://github.com/username # change to your github homepage
    # Uncomment below to add more social links
    # - https://www.facebook.com/username
    # - https://www.linkedin.com/in/username

```
To comment it's as simple as placing a '#' in the spot but if you need to take a comment out you need to make sure the - lines up

```yaml
social:
  # Change to your full name.
  # It will be displayed as the default author of the posts and the copyright owner in the Footer
  name: your_full_name
  email: example@domain.com # change to your email address
  links:
    # The first element serves as the copyright owner's link
    - https://twitter.com/username # change to your twitter homepage
    - https://github.com/username # change to your github homepage
    # Uncomment below to add more social links
      - https://www.facebook.com/username
    # - https://www.linkedin.com/in/username
```

Not like this they need to all be in one line so ensure you have them spaced accordingly. 

The avatar section is where your Profile Picture goes, simple place your photo inside the assets folder and in VS Code click, Drag and hold shift to place the file path to your avatar. 

## Posting

Another section which has some interesting parts is your post, they are all done in markdown text then converted into Markup when Jekyll runs.

All your post go into the `_post` folder you need to follow a specfic naming convention to allow this to work which is simple name your file

```file
YEAR-MONTH-DAY-title.md
```
Using dashes to seperate them instead of spaces. 

Like so 


```file
2023-04-05-WSL2-terminal-config.md
2023-04-08-Build-a-Jekyll-Website
```

All your post files are done in Markdown which is pretty easy to pickup really fast

If you run into an error where you can see your Images on your local side but your deploy is failing/not seeing the images displayed all you need to do is remove the "`..`" in the path of your images


![Alt text](/assets/2023-04-07-Build-a-Jekyll-Website%20IMG/Right%20Path.png)

The top one is the correct pathing at least that is what worked for me. 

but if you need some more information about it:

See more post formatting rules on the [Jekyll site](https://jekyllrb.com/docs/posts/)

## GitHub Pages

Before you can finilize and deploy any of your posts you need to set up your repository 


## Last Steps

When your done writing a post you can either use the CLI to deploy changes and commit and push them up to github or you can you use VS Code Workspaces like i do and commit and push them with a simple comment. 

but here's the CLI commit and push commands anyways. 

To see what you have pending you can also use 

```bash
git status
```
* `git add .` Will stage your changes
* `git commit -m` Will commit your changes to the main branch
* `git push` Will push it out to GitHub

```Bash
git add .
git commit -m "The change you Made"
git push
```

To do it in VS Code all you need to do is go to the Source Control Section

Press Commit and Push 

![Alt text](/assets/2023-04-07-Build-a-Jekyll-Website%20IMG/Soruce%20Control.png)

It will open a seperate file asking you to make a comment just comment something and then `Ctrl + S` and then once you close the comment file it will push it to GitHub.