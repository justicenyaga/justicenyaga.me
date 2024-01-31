+++
title = 'Setting up Ubuntu Desktop Environment on Wsl2'
date = 2024-01-31T02:31:15+03:00
draft = true
+++

## Introduction

If you've encountered difficulties while configuring the Ubuntu desktop environment on WSL2, fret not. Here's a quick guide to help you through the process.

## Step 1: Update Your Package Manager

Ensure your package manager is up-to-date using the following command:

```bash
sudo apt update
```

## Step 2: Install Ubuntu Desktop and Mesa-utils

Install the necessary packages for the Ubuntu desktop and mesa-utils:

```bash
sudo apt install ubuntu-desktop mesa-utils
export DISPLAY="$(grep nameserver /etc/resolv.conf | sed 's/nameserver //'):0"
export LIBGL_ALWAYS_INDIRECT=0
```

## Step 3: Install VcXsrv on Windows

On the Windows side, install [VcXsrv](https://sourceforge.net/projects/vcxsrv/). After installation, choose the following set-up options:

- Multiple windows
- Display 0
- Start no client
- Disable native OpenGL (sic)

## Troubleshooting: "Transport endpoint is not connected"

If you encounter the error "Transport endpoint is not connected" while setting up the Ubuntu desktop, follow these steps:

1. Press `<C-c>` to skip packages with the error.
2. Run the following commands:

```bash
sudo mv /etc/acpi/events /etc/acpi/events.bak
sudo ln -s /dev/null /etc/systemd/system/acpid.service
sudo ln -s /dev/null /etc/systemd/system/acpid.path
```

Now you should be good to go!

Happy Coding!
