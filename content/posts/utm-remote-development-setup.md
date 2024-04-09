---
title: "Setting Up a Linux Development Environment on Apple Silicon Mac with UTM and VSCode Server"
date: 2024-04-09T10:39:11+02:00
draft: false
---

# Simplifying Linux Development on MacOS
In certain projects, you might find yourself needing to work with Linux due to compatibility issues that MacOS can't handle. While using virtual machines (VMs) has been a common workaround, it comes with its own set of challenges such as speed limitations, display problems, and the inconvenience of switching between MacOS and Ubuntu interfaces.

This guide aims to address these issues by setting up a Linux VM without a display and using the VSCode remote-SSH plugin for smooth remote development.

## Prerequisites
Before getting started, make sure you have:

- **UTM**: Download and install UTM from [here](https://mac.getutm.app/).
- **Ubuntu Server ISO for ARM**: Get the Ubuntu server ISO build for ARM from [here](https://ubuntu.com/download/server/arm).

## Step-by-Step Guide

### Setting Up the VM
Start by following the instructions provided in the guide for configuring a Ubuntu VM within UTM, available [here](https://docs.getutm.app/guides/ubuntu/). I allocated 8GB of RAM during setup.

### Booting the VM
When you boot the VM for the first time, choose the Install or Try Ubuntu option and proceed with the installation steps. Make sure to enable OpenSSH Server during setup and eject the ISO before rebooting.

### Setup Rendezvous
To simplify SSH access to the VM, install the `avahi-daemon`, which enables the use of `ssh hostname.local`:

```bash
sudo apt install avahi-daemon
```

### Removing the Display
Since we can now SSH into the VM, the display becomes unnecessary. Remove the display by going to the VM settings in UTM, right-clicking on `Display`, and selecting `Remove`.

### VSCode Remote SSH
If you're using JetBrains IDEs, you can also consider using the `Remote Development` feature.

- Install the `remote SSH` plugin by Microsoft.
- Open the command palette with `Cmd-Shift-P`, run `Remote-SSH: Add New SSH Host…`, and enter your SSH command, e.g., `ssh user@hostname.local`.
- In the bottom left corner of VSCode, click on the blue rectangle with two arrows to access `Connect to Host...`, where you can select the recently added host for seamless remote development.

By following these steps, you can improve your development workflow by seamlessly integrating Linux development into MacOS, effectively overcoming compatibility challenges.