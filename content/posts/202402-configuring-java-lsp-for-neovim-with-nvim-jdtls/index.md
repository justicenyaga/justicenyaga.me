+++
title = "Configuring Java LSP, and Debugger for Neovim with nvim-jdtls"
date = 2024-02-05T16:36:17+03:00
draft = false
tags = ["neovim", "nvim-lspconfig", "nvim-jdtls"]
+++

## Introduction

Developing Java code in Neovim can be a seamless experience with the right Language Server Protocol (LSP) setup. In this blog post, we will explore how to enhance your Neovim environment for Java development by configuring `nvim-jdtls`. This plugin, available at [nvim-jdtls](https://github.com/mfussenegger/nvim-jdtls), offers a comprehensive set of features tailored for Java, addressing challenges such as navigating to the definition of methods and classes outside your project.

Before we proceed, ensure you've checked out my Neovim configuration post, which complements this setup:

{{< article link="/posts/202401-my-neovim-configuration/" >}}

## Prerequisites

1. **Neovim version >= 0.6.0**

   Verify your Neovim version using:

   ```bash
   nvim --version
   ```

2. **Java runtime environment 17 and above**

   Install the desired Java version, ensuring it is 17 or above. For example, to install OpenJDK version 21:

   ```bash
   sudo apt install openjdk-21-jdk
   ```

   Set the `JAVA_HOME` environment variable to point to the JDK or JRE directory. Identify the correct path using:

   ```bash
   sudo update-alternatives --config java
   ```

   Set `JAVA_HOME` in your `.bashrc` or `.zshrc`:

   ```bash
   export JAVA_HOME=/path/to/openjdk-21
   ```

   For example:

   ```bash
   export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
   ```

3. **eclipse.jdt.ls**

   Download and extract a snapshot build from [http://download.eclipse.org/jdtls/snapshots/](http://download.eclipse.org/jdtls/snapshots/):

   ```bash
   wget https://download.eclipse.org/jdtls/snapshots/jdt-language-server-1.31.0-202312211634.tar.gz && sudo tar -C /usr/local -xzf jdt-language-server-1.31.0-202312211634.tar.gz
   ```

4. **java-debug**
   To debug java programs, load the `java-debug` extension. Install it on your neovim data folder `~/.local/share/nvim` using the following commands

   ```bash
   git clone https://github.com/microsoft/java-debug.git ~/.local/share/nvim/java-debug
   cd ~/.local/share/nvim/java-debug
   ./mvnw clean install
   ```

## Installing plugins

### 1. nvim-jdtls

Install the plugin using your preferred plugin manager. If using Lazy, add the following line to your init.lua file and install with `:Lazy`:

```lua
"mfussenegger/nvim-jdtls", -- java lsp
```

### 2. nvim-dap

Install [nvim-dap](https://github.com/mfussenegger/nvim-dap) using your preferred plugin manager. Check out my [nvim-dap configuration](https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/lua/justice/plugins/dap.lua) which provides a user-friendly UI as well as key mappings for debugging.

### 3. jdtls LSP

Install `jdtls` lsp using Mason by initiating mason with `:Mason` and proceeding with the installation. Check out my [Mason configuration](https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/lua/justice/plugins/lsp/mason.lua) if you haven't setup Mason. Mason is just a plugin for managing LSPs, linters, formatters, and DAPs.

## Configuration

### 1. Avoid confict between nvim-lspconfig and nvim-jdtls

Skip this step if you are not using `nvim-lspconfig`.

To avoid conficts, ensure you do not run `nvim-lspconfig` and `nvim-jdtls` simultaneously. Add the following setup_handler configuration to your `nvim-lspconfig` (in my case it's `~/.config/nvim/lua/justice/plugins/lsp/lspconfig.lua`):

```lua
-- empty function to ignore jdtls
local noop = function() end

require("mason-lspconfig").setup_handlers({
  function(server_name)
    lspconfig[server_name].setup({
      on_attach = on_attach,
      capabilities = capabilities,
    })
  end,
  ["jdtls"] = noop,
})
```

### 2. jdtls configuration

Create a `~/.config/nvim/ftplugin/java.lua` file with the following code for jdtls configuration:

```lua
local jdtls_bin = vim.fn.stdpath("data") .. "/mason/bin/jdtls"

local keymap = vim.keymap

local opts = { noremap = true, silent = true }

local lsp_attach = function(client, bufnr)
  require("jdtls.dap").setup_dap_main_class_configs() -- Discover main classes for debugging

  opts.buffer = bufnr

  -- set keybinds. Copied my lspconfig keybinds here
end

local config = {
  cmd = { jdtls_bin },
  root_dir = vim.fs.dirname(vim.fs.find({ "gradlew", ".git", "mvnw" }, { upward = true })[1]),
  on_attach = lsp_attach,
  init_options = {
    bundles = {
      vim.fn.glob(vim.fn.stdpath("data") .. "/java-debug/com.microsoft.java.debug.plugin/target/com.microsoft.java.debug.plugin-*.jar", 1),
    },
  },
}
require("jdtls").start_or_attach(config)
```

### 3. nvim-dap configuration

Given that you have already installed `nvim-dap`, nvim-jdtls provides integration with nvim-dap, so you don't need to configure Java debug adapters; nvim-jdtls adds that for you automatically. The only thing you'll need to do is add a java configuration for debugging. Check out their [wiki](https://github.com/mfussenegger/nvim-dap/wiki/Java) for more details. Add the following configuration to your `nvim-dap` plugin configuration file

```lua
require("dap").configurations = {
  java = {
    {
      type = "java",
      name = "Debug",
      request = "launch",
      program = "${file}",
    },
  },

  -- configurations for other languages
}
```

## My configuration files

Explore my configuration files by visiting [lspconfig.lua](https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/lua/justice/plugins/lsp/lspconfig.lua), [java.lua](https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/ftplugin/java.lua) and [dap.lua](https://raw.githubusercontent.com/justicenyaga/my_nvim_config/master/lua/justice/plugins/dap.lua).

## Conclusion

Kudos on completing the setup! Your Neovim environment is now finely tuned for Java development with the configured Java LSP. Wishing you smooth coding sessions ahead - Happy coding!
