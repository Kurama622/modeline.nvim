# modeline.nvim

![modeline](https://github.com/user-attachments/assets/6f469213-7163-49f9-8444-2a85f93283c3)

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
        p.pos(),
      })
    end,
  },
```

## Look Here

The original author's repository: [https://github.com/nvimdev/modeline.nvim](https://github.com/nvimdev/modeline.nvim), please give it a star; I've just modified some styles and made it configurable.

# GPL v3
