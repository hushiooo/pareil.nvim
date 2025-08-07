# pareil.nvim

**🧬 Compare any two Git-tracked files across branches, side by side — inside Neovim.**

`pareil.nvim` is a lightweight, asynchronous Neovim plugin that lets you diff two files from any Git branch using Telescope pickers and a floating popup window.

---

## ✨ Features

- 📂 Interactive selection of **two files** from your Git repo
- 🌿 Choose **two branches** (from local refs) to diff from
- 🧠 Uses Neovim’s built-in `vim.diff()` engine
- 🪟 Displays the diff in a **centered floating popup**, syntax-highlighted
- ⚡ Fully **asynchronous**, no UI blocking
- 🛡️ Safe and robust — handles edge cases, errors, and invalid inputs gracefully

---

## 📦 Installation

### [lazy.nvim](https://github.com/folke/lazy.nvim)

```lua
{
  "hushiooo/pareil.nvim",
  config = true,
  keys = {
    { "<leader>pd", "<cmd>PareilsDiff<CR>", desc = "Pareils diff (popup)" }
  },
  dependencies = {
    "nvim-lua/plenary.nvim",
    "nvim-telescope/telescope.nvim",
  },
}
```

### [packer.nvim](https://github.com/wbthomason/packer.nvim)

```lua
use({
  "hushiooo/pareil.nvim",
  config = function()
    require("pareil").setup()
  end,
  requires = {
    "nvim-lua/plenary.nvim",
    "nvim-telescope/telescope.nvim",
  },
})
```

## Usage

### Via Command

:PareilsDiff

### Via keymap

```lua
vim.keymap.set("n", "<leader>pd", function()
  require("pareil").open()
end, { desc = "Pareils diff (popup)", silent = true })
```


## Config

```lua
require("pareil").setup({
  delta_width = 120, -- Width of popup window
})
```
