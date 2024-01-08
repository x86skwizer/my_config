# Configuration Setup Script

This script automates the setup of my preferred configurations for the terminal environment. It performs the following tasks:

1. Checks for root permissions to ensure proper execution.
2. Resets the terminal screen for a clean start.
3. Updates the operating system packages.
4. Upgrades existing software and the operating system.
5. Installs Tmux and adds the `tmux-themepack`.
6. Installs oh-my-bash for an enhanced bash shell experience.
7. Installs the `fonts-powerline` package for oh-my-bash config.
8. Installs Neovim and adds the NvChad config.

## Usage

Make sure to run this script with root permissions:

```bash
sudo bash my_config
```

## Note

While working with Neovim, in case of `Warning: multiple different client offset_encodings detected for buffer`, in `custom/config/lspconfig.lua` at the top you need to add these lines:

```
local on_attach = require("plugins.configs.lspconfig").on_attach
local capabilities = require("plugins.configs.lspconfig").capabilities
capabilities.offsetEncoding = { "utf-16" }
```

If you want tab characters in your file to appear 4 character cells wide, go to `./config/nvim/lua/core/`, open `init.lua` and change these lines:

```
-- Indenting
opt.expandtab = false
opt.shiftwidth = 4
opt.smartindent = true
opt.tabstop = 4
opt.softtabstop = 4
```

For my usual Tmux config and .bashrc:

```bash
cp .tmux.conf ~
cp .bashrc ~
```

This script assumes you are using a Debian-based Linux distribution with `apt` package manager. If you are using a different distribution or package manager, you may need to adjust the commands accordingly.

## Disclaimer

Use this script at your own risk. It is recommended to review the script and understand the commands before executing it on your system.

## AUTHORS

[x86skwizer](https://github.com/x86skwizer)  &  [mberrouk](https://github.com/mberrouk)
