+++
title = "My Tmux Configuration"
date = 2024-01-20T14:47:38+03:00
draft = false
tags = ['tmux', 'neovim']
+++

## Introduction

Tmux is a terminal multiplexer; it allows multiple terminal sessions to be accessed from a single window.

In this article, we'll walk through my Tmux setup that is designed for efficient integration with Neovim.

## Screenshots

![MyTmux](tmux.png)

## Configuration

Follow these steps to set up Tmux:

1. **Install Tmux:**

   If Tmux is not already installed on your system, you can install it using your package manager. For example, on Debian-based systems, run:

   ```bash
   sudo apt-get install tmux

   ```

   Verify the installation by checking the Tmux version:

   ```bash
   tmux -V
   ```

2. **Retrieve My Configuration File:**

   Download my Tmux configuration file into your home directory using the following command:

   ```bash
   wget https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/.tmux.conf -O ~/.tmux.conf

   ```

3. **Install Tmux Plugin Manager (tpm):**

   Clone the Tmux Plugin Manager repository to `~/.tmux/plugins/` using:

   ```bash
   git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
   ```

4. **Create a Tmux session:**

   Start a new Tmux session.

   ```bash
   tmux new -s SessionName
   ```

   This should create a session and attach you to the created session.

5. **Reload the Tmux configuration file:**

   Press your Tmux prefix key (my configuration uses `Ctrl + Space`) followed by `r` to reload the configuration file:

   ```bash
   <C-Space>r
   ```

   {{< alert icon="none" >}}
   On the configuration file, replace `C-Space` with a prefered key bind to override the default prefix key bind, on the following lines:

   ```bash
   set -g prefix C-Space
   bind-key C-Space send-prefix
   ```

   {{< /alert >}}

6. **Install Tmux plugins:**

   While inside a Tmux session, install plugins by pressing your Tmux prefix key followed by `I` (uppercase):

   ```bash
   <C-Space>I
   ```

   {{< alert icon="none" >}}
   Again, replace `<C-Space>` with your configured prefix key bind.
   {{< /alert >}}

That's it! Your Tmux environment is now configured with the specified settings and plugins. Customize further based on your preferences.

## Usage

### Normal Keymaps

{{<table "table table-striped table-bordered">}}

| **Keybind**        | **Description**      |
| ------------------ | -------------------- |
| `C-Space`          | Prefix key           |
| `prefix + \|`      | Vertical split       |
| `prefix + -`       | Horizontal split     |
| `prefix + r`       | Reload configuration |
| `prefix + j/k/l/h` | Resize panes         |
| `prefix + m`       | Maximize pane        |

{{</table>}}

### Copy Mode Keymaps

{{<table "table table-striped table-bordered">}}

| **Keybind**  | **Description** |
| ------------ | --------------- |
| `prefix + [` | Enter copy mode |
| `v`          | Start selection |
| `y`          | Copy selection  |
| `q`          | Exit copy mode  |

{{</table>}}

Remember to customize these keybinds further based on your preferences and workflow!
