---
title: Windows WSL2 Terminal Config aka OhMyZsh
date: 2023-04-05 02:51:00 -500
categories: [homelab, windows]
tags: [homelab,wsl,terminal,windows,zsh,linux]
---

# OhMyZsh Windows WSL Config

Today we are going to be installing Linux on a Windows Machine and configuring the shell to use OhMyZsh so you can freely copy and paste commands in a UNIX like enviroment.

## Prerequisite

Simple all you need to get started is a Windows Machine

### What were going to be doing
* Get the Windows Terminal installed from Microsoft Store
* Turn on Windows Subsystem for linux or (WSL2)
* Download a Flavor a Linux in my case Ubuntu 20.04.5 LTS
* Change default Windows Terminal to Ubuntu
* run commands to install OhMyZsh

#### Step 1

Go to the Microsoft Store and download and install Windows Terminal

![Alt text](/assets/2023-04-05%20WSL2%20Terminal%20Config%20IMG/get%20windows%20terminal.png)

#### Step 2

 Turn on Windows Subsystem for Linux. In the Windows Search bar type "Turn Windows Features on" 

 Then turn on either Windows Subsystem for linux (WSL1) or Virtual Machine Platform (WSL2) depending on what version on WSL you want to use I will be using WSL2

![Alt text](/assets/2023-04-05%20WSL2%20Terminal%20Config%20IMG/Turn%20on%20WSL2.png)

#### Step 3

 Go to the Microsoft Windows Store download and install whatever version of Linux you want. I decided to go with Ubuntu 20.04.5 LTS but any of them should work.

![Alt text](/assets/2023-04-05%20WSL2%20Terminal%20Config%20IMG/Microsoft%20store%20Ubuntu.png)

 Once downloaded you can open your Linux distro and allow it to install as well as create your first user, It will prompt you to create a Username and Password

 Now Close out the System and open Microsoft Terminal. 

 Click the drop down arrow and go to "Settings" on the "Startup" page simple change "Default profile" to your Linux OS of choice. 

![Alt text](/assets/2023-04-05%20WSL2%20Terminal%20Config%20IMG/Terminal%20Default%20Profile.png)

#### Step 4

Finally Open your Linux Distro if it isn't opened already

We are going to enter in commands first we are going to update and download the package information best practice to do this on all new Linux Machines. 
```bash
sudo apt update
```

This will prompt you to enter in your sudo password which is the password you created in the beginning

Now we will install zsh which is the shell also known as zshell comes with some new features like 
* Automatic cd
* spelling correction like if you make a mistake typing a directory it'll try and fix it for you
* Lastly Plugin and Theme support

To install zsh 
```bash
sudo apt install zsh
```
If done correctly it will ask you to type -y which means yes saying yes confirm download.

I like to install new fonts so it looks nice and pretty this will also prompt you to do a -y to confirm 

```bash
sudo apt-get install powerline fonts-powerline
```

Lastly installing OhMyZsh all you need to do is run one more command When you run this command it will ask you 2 things 1 being do you want to make this the default type y for yes. and it will prompt you to enter in your sudo password.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

![Alt text](/assets/2023-04-05%20WSL2%20Terminal%20Config%20IMG/All%20done%20oh%20my%20zsh.png)

If you see this then boom its installed and you will have a cleaner and colorful UNIX experience 

If you don't see this then you might have missed a step