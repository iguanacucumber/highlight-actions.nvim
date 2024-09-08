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
    actions = {
      Undo = {
        disabled = false,
        fg = '#dcd7ba',
        bg = '#2d4f67',
        mode = 'n',
        keymap = 'u', -- mapping
        cmd = 'undo', -- Vim command
        opts = {}, -- silent = true, desc = "", ...
      },
      Redo = {
        disabled = false,
        fg = '#dcd7ba',
        bg = '#2d4f67',
        mode = 'n',
        keymap = '<C-r>',
        cmd = 'redo',
        opts = {},
      },
      Pasted = {
        disabled = false,
        fg = '#dcd7ba',
        bg = '#2d4f67',
        mode = 'n',
        keymap = 'p',
        cmd = 'put',
        opts = {},
      },
    -- Any other actions you might wanna add
    },
  },
},
```

> [!NOTE]
> This plugin is a fork of [highlight-undo.nvim](https://github.com/tzachar/highlight-undo.nvim)
