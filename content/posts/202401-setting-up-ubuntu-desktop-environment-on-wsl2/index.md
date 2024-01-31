+++
title = "Setting up Ubuntu Desktop Environment on WSL2"
description = "A comprehensive guide to installing and configuring the Ubuntu Desktop environment on Windows Subsystem for Linux 2 (WSL2). Enhance your development environment and streamline your coding experience with this step-by-step walkthrough."
summary = "A comprehensive guide to installing and configuring the Ubuntu Desktop environment on Windows Subsystem for Linux 2 (WSL2). Enhance your development environment and streamline your coding experience with this step-by-step walkthrough."
date = 2024-01-31T02:31:15+03:00
draft = false
tags = ["wsl2", "ubuntu", "ubuntu-desktop", "vcxsrv"]
+++

## Introduction

Welcome to this comprehensive guide on installing and configuring Ubuntu Desktop environment on Windows Subsystem for Linux 2 (WSL2). Enhance your development environment and streamline your coding experience with this step-by-step walkthrough.

This post assumes that you have already installed Ubuntu within WSL2. If not, please do install it before proceeding.

## Step 1: Install Ubuntu Desktop and Mesa-utils

Begin by installing the Ubuntu Desktop and mesa-utils packages:

```bash
sudo apt update
sudo apt install ubuntu-desktop mesa-utils
```

### Troubleshooting for "Transport endpoint is not connected" error

If you encounter the error "Transport endpoint is not connected" during the setup, perform the following troubleshooting steps:

1. Press `Ctrl + C` to skip packages with the error.
2. Run the following commands:

```bash
sudo mv /etc/acpi/events /etc/acpi/events.bak
sudo ln -s /dev/null /etc/systemd/system/acpid.service
sudo ln -s /dev/null /etc/systemd/system/acpid.path
```

Run the following command to reconfigure the unpacked packages that were skipped on the previous step.

```bash
sudo dpkg --configure -a
```

## Step 2: Set Up Environment Variables

Configure environment variables for persistent settings. It's recommended to add these to your `.bashrc` or `.zshrc`:

```bash
export DISPLAY="$(grep nameserver /etc/resolv.conf | sed 's/nameserver //'):0"
export LIBGL_ALWAYS_INDIRECT=0
```

## Step 3: Install VcXsrv on Windows

On the Windows side, install [VcXsrv](https://sourceforge.net/projects/vcxsrv/). After installation, choose the following setup options:

- Multiple windows
- Display number: 0
- Start no client
- Check everything on Extra settings, that is, clipboard, primary selection, Native opengl, Disable access control

  You can save the configuration for future use

- Click finish to start the server

## Step 4: Verify Installation with xeyes

Ensure VcXsrv is running and test the setup by opening xeyes app or any other installed desktop app such as firefox on your WSL terminal:

```bash
xeyes
```

## Conclusion

The successful opening of the xeyes app indicates that you have seamlessly set up the Ubuntu Desktop environment on WSL2. Happy coding!
