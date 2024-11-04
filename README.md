# modeline.nvim

![modeline](https://github.com/user-attachments/assets/2c6166fc-88d0-4d04-bd33-0246e2b48195)

implement emacs default modeline on neovim.

- async using coroutine
- event drive
- blazing fast than any statusline plugin
- Lsp progress message
- minimalist

## Configuration

- lazy.nvim

```lua
  {
    "Kurama622/modeline.nvim",
    event = { "BufReadPost */*" },
    config = function()
      vim.api.nvim_set_hl(0, "Statusline", { fg = "skyblue", bg = "NONE" })
      local p = require("modeline.provider")
      require("modeline").setup({
        p.mode(),
        p.eol(),
        p.filestatus(),
        p.separator(),
        p.fileinfo(),
        p.separator(),
        p.gitinfo(),
        p.space(),
        p.leftpar(),
        p.filetype(),
        p.diagnostic(),
        p.rightpar(),
        p.progress(),
        p.lsp(),
        p.space(),
        p.space(),
        p.pos(),
      })
    end,
  },
```

# GPL v3
