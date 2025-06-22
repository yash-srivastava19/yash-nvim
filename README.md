# yash-nvim
Barebones init.lua for my neovim. 

---

# Neovim Configuration for Windows.

VSCode good, NeoVim hard.

Whenever I try to switch to Vim, the sheer complexity makes me quit very easily. I've tried getting Vim bindings in VSCode, but I just quickly disable it and get to my old habits. Things are difficult to change, so this is my replication of doing what I do in VSCode, but in Vim. Hope I get Vim pilled very soon. I'll try to keep practicing. Below is a GPT summary of what this config contains. 

---

## Features

This Neovim configuration is designed to provide a fast, modern, and extensible development experience on Windows. It leverages the Lazy.nvim plugin manager to load plugins efficiently and supports language servers, formatting, fuzzy search, version control integration, and a custom dashboard. The setup is built with usability in mind and includes quality-of-life improvements for both editing code and navigating projects.

![image](https://github.com/user-attachments/assets/627cb385-b556-4589-9da4-cf7a0491bc1d)


### Plugin Highlights

* **File Explorer**: Integrated `nvim-tree` for directory navigation with icon support.
* **Floating Terminal**: `toggleterm.nvim` configured as a vertical split with toggle support.
* **Fuzzy Finder**: `telescope.nvim` for searching files, buffers, and performing live grep.
* **Buffer Management**: `bufferline.nvim` provides a tab-like experience for buffers.
* **Language Server Protocol (LSP)**: Configured with `pyright` and `tsserver` using `mason.nvim` and `nvim-lspconfig`.
* **Autocompletion**: Lightweight completion via `nvim-cmp` with LSP integration.
* **Formatting**: Configured using `conform.nvim` with support for Python (`black`) and Lua (`stylua`).
* **Syntax Highlighting**: Enabled through `nvim-treesitter` with support for multiple languages.
* **Version Control**: Git signs and diff highlighting via `gitsigns.nvim`.
* **Diagnostics UI**: Toggleable diagnostics panel with `trouble.nvim`.
* **Startup Dashboard**: A custom Doom-style interface using `alpha.nvim`.
* **Statusline**: Clean, theme-aware statusline using `lualine.nvim`.
* **UI Enhancements**: Smooth scrolling and visual indent guides via `neoscroll.nvim` and `indent-blankline.nvim`.
* **Theme Support**: Preinstalled themes including Catppuccin, TokyoNight, OneDark, Gruvbox, Rose Pine, Nord, and Oxocarbon (default).

---

![image](https://github.com/user-attachments/assets/46546201-d49d-4c46-a9e5-942be94ee1f1)


## Installation

This configuration is optimized for Windows. Ensure you have the following installed:

1. **Neovim v0.10+**
   Download from the [Neovim GitHub releases](https://github.com/neovim/neovim/releases).

2. **Git**
   Required for plugin management (`git-scm.com`).

3. **ripgrep**
   Required for Telescope’s file and text searching.

4. **Fonts**
   A patched Nerd Font is recommended for proper icon rendering. You can use fonts like [JetBrains Mono](https://www.jetbrains.com/lp/mono/) or [FiraCode Nerd Font](https://www.nerdfonts.com/).

### Setup

1. Place your `init.lua` file under:

   ```
   C:\Users\<your-username>\AppData\Local\nvim\init.lua
   ```

2. Launch Neovim. The first startup will automatically clone and install all plugins using Lazy.nvim.

3. Restart Neovim to apply all settings.

---

## Key Bindings

This configuration uses `<Space>` as the leader key.

### Core

* `<leader>e` : Toggle file explorer (NvimTree)
* `<leader>tt` : Open terminal in a vertical split
* `<leader>\`` : Toggle between terminal and last active window (like VSCode Ctrl+\`)
* `<leader>vc` : Edit the current Neovim config (`init.lua`)
* `<leader>xx` : Open or close the Trouble diagnostics panel

### File Navigation (Telescope)

* `<leader>ff` : Find files in the current directory
* `<leader>fg` : Search text (live grep)
* `<leader>fb` : Show open buffers
* `<leader>tc` : Pick a colorscheme

### Buffer and Window Management

* `<Tab>` : Next buffer
* `<Shift-Tab>` : Previous buffer
* `<leader>c` : Close current buffer

---

## Dashboard

The startup screen is powered by `alpha.nvim` with a custom Doom-inspired ASCII art header and the following shortcuts:

* `e` – New file
* `f` – Find file (Telescope)
* `r` – Recent files
* `c` – Edit config
* `q` – Quit Neovim

This provides quick access to commonly used actions directly upon launch.

---

## Themes

Multiple themes are preinstalled. You can change the default theme by editing the following line in `init.lua`:

```lua
vim.cmd.colorscheme("oxocarbon")
```

Available options include:

* `"catppuccin"`
* `"tokyonight"`
* `"onedark"`
* `"gruvbox"`
* `"rose-pine"`
* `"nord"`
* `"oxocarbon"`

---

## Language Support

Language servers are configured for:

* **Python** (`pyright`)
* **JavaScript / TypeScript** (`tsserver`)

Additional LSPs can be installed via the `:Mason` interface or by modifying the LSP config block.

---

## Formatting

The following formatters are automatically applied on save:

* Lua → `stylua`
* Python → `black`

You can extend this to other filetypes using `conform.nvim`.

---

## Notes

* Terminal switching behaves like VSCode — use \`<leader>\`\` to toggle in and out quickly.
* Caps Lock has been remapped to act as `Esc` (requires OS-level remapping, e.g., SharpKeys or AutoHotkey).
* All configurations are self-contained and modular.

---
