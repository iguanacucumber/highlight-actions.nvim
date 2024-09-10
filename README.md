# highlight-actions.nvim

Highlight changed text after an operation. Purely lua / nvim api implementation,
no external dependencies needed.

https://github.com/user-attachments/assets/4e5bfa62-c53c-4842-a09c-102508d2efd4

## ✨ Installation

Using Lazy:

```lua
{
  'iguanacucumber/highlight-actions.nvim',
  keys = { "u", "p", "<C-r>" }, -- Lazy load on keymap
-- opts = {}, -- for a default config
  opts = {
    highlight_for_count = true, -- Should '3p' or '5u' be highlighted
    duration = 300, -- Time in ms for the highlight
    after_keymaps = function() end, -- Any keymaps you might wanna add after the keymaps set by this plugin
    actions = {
      Undo = {
        disabled = false, -- Useful when debugging
        fg = "#dcd7ba", -- colors
        bg = "#2d4f67",
        mode = "n", -- The mode(s)
        keymap = "u", -- mapping
        cmd = "undo", -- Vim command
        opts = {}, -- silent = true, desc = "", ...
      },
      Redo = { keymap = "<C-r>", cmd = "redo" }, -- Actions can be made as easely as this
      Pasted = {
        keymap = "p",
        cmd = "put",
        cmd_args = function() -- This function needs to return a string as a parameter to cmd
          return vim.v.register -- Return the register
        end,
      },
    -- Any other actions you might wanna add
    },
  },
},
```

> [!NOTE]
> This plugin is a fork of [highlight-undo.nvim](https://github.com/tzachar/highlight-undo.nvim)
