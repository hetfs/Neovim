# 🚀 The Essential `lazy.nvim` Guide

_The definitive guide to supercharging Neovim with the fastest plugin manager – minimalist yet powerful._

## ⚡ **Why Choose `lazy.nvim`?**

- 🚀 **Lightning Fast** – Parallel installation & updates
- 🧩 **Declarative Setup** – Manage plugins like `package.json`
- 📊 **Built-in Dashboard** – `:Lazy` for updates, health checks, and profiling
- ⏱️ **Smart Loading** – Load plugins only when needed for faster startup

---

## 🛠️ **Getting Started in 2 Steps**

### 1. **Installation**

Add to your `init.lua`:

```lua
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not vim.loop.fs_stat(lazypath) then
  vim.fn.system({
    "git",
    "clone",
    "--filter=blob:none",
    "https://github.com/folke/lazy.nvim.git",
    "--branch=stable",  -- Recommended: stable releases
    lazypath,
  })
end
vim.opt.rtp:prepend(lazypath)
```

### 2. **Plugin Setup**

Organize plugins in `lua/plugins/`:

```lua
require("lazy").setup("plugins")  -- Loads all `lua/plugins/*.lua` files
```

**Example (`lua/plugins/editor.lua`):**

```lua
return {
  -- Basic plugin (always loaded)
  "nvim-lualine/lualine.nvim",

  -- Load only when pressing `<leader>`
  {
    "folke/which-key.nvim",
    keys = "<leader>",
    config = function() require("which-key").setup() end,
  },

  -- Load only for LaTeX files
  {
    "lervag/vimtex",
    ft = "tex",
  },
}
```

---

## ⚡ **Performance Boost Tips**

### **Smart Loading Triggers**

```lua
{
  "nvim-telescope/telescope.nvim",
  cmd = "Telescope",    -- Load on command
  event = "BufReadPre", -- Load when opening files
  keys = "<leader>ff",  -- Load on keypress
  ft = "python",        -- Load for filetype
  dependencies = { "nvim-lua/plenary.nvim" },
}
```

### **Diagnose Slow Plugins**

Run `:Lazy profile` to identify startup bottlenecks.

---

## 🔧 **Pro Techniques**

### **Conditional Loading**

```lua
{
  "neovim/nvim-lspconfig",
  cond = function()
    return vim.fn.executable("node") == 1  -- Requires Node.js
  end,
}
```

### **Custom Plugin Settings**

```lua
{
  "akinsho/bufferline.nvim",
  version = "*",       -- Latest stable
  branch = "main",     -- Dev branch
  priority = 1000,     -- Load first
  opts = {             -- Default config
    options = { separator_style = "slant" }
  },
}
```

---

## ❓ **Quick Help**

**Q:** How to update plugins?  
→ `:Lazy update`

**Q:** How to remove a plugin?  
→ Delete from config + run `:Lazy clean`

---

## 🌟 **Plugin Recommendations**

Explore [curated plugins](https://www.lazyvim.org/plugins) for inspiration.

---

## 💡 **Share Your Tips!**

Contributions welcome! Share your `lazy.nvim` optimizations.
