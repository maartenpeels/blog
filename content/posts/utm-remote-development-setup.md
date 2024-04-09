---
title: "Setting Up a Linux Development Environment on Apple Silicon Mac with UTM and VSCode Server"
date: 2024-04-09T10:39:11+02:00
draft: false
---

## Overview
For some projects I need to build and run on Linux because the code is not compatible with MacOS. To do this I've used VM's in the past, but there are some downsides to this:
- Speed
- Rendering / Resolution
- Having 2 different UI's (MacOS / Ubuntu)

This guide aims to solve these issues by setting up a Linux VM without a display and using the VSCode remote-SSH plugin. This plugin allows for, as the name implies, remote development. When first connecting it will automatically install VSCode Server.

### Prerequisites
- Download and install UTM. You can find it [here](https://mac.getutm.app/).
- Download an Ubuntu server ISO build for ARM [here](https://ubuntu.com/download/server/arm).

## Steps

### Setup VM
I basically followed the guide for setting up a Ubuntu VM within UTM. You can find this guide [here](https://docs.getutm.app/guides/ubuntu/). The only change I've made is that I gave it 8GB of RAM.

### Boot the VM
When booting for the first time select `Install or Try Ubuntu`. Follow the steps to install Ubuntu.

- During the installation steps make sure to enable `OpenSSH Server`.
- Eject the ISO before rebooting.

### Setup Rendezvous
To be able to more easily SSH into the VM we can install the `avahi-daemon`. Doing this allows `ssh hostame.local`

- `sudo apt install avahi-daemon`

### Remove Display
Now we are able to SSH into the VM we do not need a display anymore. We can remove the display by going to the VM settings in UTM and right clicking the `Display` and selecting `Remove`.

### VSCode Remote SSH
Note: There is also an option to setup `Remote Toolchains` in JetBrains IDE's if you are using that.

- Install the `remote SSH` plugin by Microsoft.
- Press `Cmd-Shift-P` to open the command pallete, run `Remote-SSH: Add New SSH Host…` and enter your ssh command, e.g: `ssh user@hostname.local`
- In the bottom left of VSCode there is a blue rectangle with 2 arrows in it, when you click this you can select `Connect to Host...`. Here you will be able to select the host that we just added.