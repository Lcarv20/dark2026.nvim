# dark2026.nvim

A Neovim port of VS Code's **Dark 2026** look — built from the official Dark Modern 2026 theme JSON.

> **Note**: This is a fork of the original colorscheme by [D0nw0r](https://github.com/D0nw0r/dark2026.nvim), featuring added support for transparent mode and custom configurations.

![dark2026.nvim](./example.png)

- Dark Modern 2026 UI palette (deep `#121314` editor, `#191a1b` chrome, cyan-blue `#3994bc` accent)
- GitHub-Dark-style syntax: **red keywords**, **purple functions**, teal-green types, light-blue constants, soft-blue macros
- Treesitter, LSP semantic tokens, diagnostics, diff, gitsigns
- Plugin highlights: blink.cmp, telescope, snacks.picker, bufferline, which-key
- **Transparent mode support**

## Install & Configuration

### lazy.nvim

```lua
{
  'Lcarv20/dark2026.nvim',
  lazy = false,
  priority = 1000,
  opts = {
    transparent = true, -- set to true for transparent background
  },
  config = function(_, opts)
    require('dark2026').setup(opts)
    vim.cmd.colorscheme 'dark2026'
  end,
}
```

### Native Neovim Package Manager (`pack`)

#### Linux / macOS
```bash
git clone https://github.com/Lcarv20/dark2026.nvim.git ~/.config/nvim/pack/plugins/start/dark2026.nvim
```

#### Windows (cmd)
```cmd
git clone https://github.com/Lcarv20/dark2026.nvim.git %USERPROFILE%\AppData\Local\nvim\pack\plugins\start\dark2026.nvim
```

#### Windows (PowerShell)
```powershell
git clone https://github.com/Lcarv20/dark2026.nvim.git $env:LOCALAPPDATA\nvim\pack\plugins\start\dark2026.nvim
```

Then in your `init.lua`:
```lua
require('dark2026').setup({
  transparent = true, -- optional
})
vim.cmd.colorscheme 'dark2026'
```

### packer.nvim

```lua
use {
  'Lcarv20/dark2026.nvim',
  config = function()
    require('dark2026').setup({
      transparent = true,
    })
    vim.cmd.colorscheme 'dark2026'
  end
}
```

### Lua / Global option

You can also call `setup()` or set `vim.g.dark2026_transparent`:

```lua
require('dark2026').setup({ transparent = true })
vim.cmd.colorscheme 'dark2026'
```

or in Vimscript:

```vim
let g:dark2026_transparent = v:true
colorscheme dark2026
```

## Options

| Option | Type | Default | Description |
|---|---|---|---|
| `transparent` | `boolean` | `false` | Disable background color for editor elements (`Normal`, `SignColumn`, etc.) |

## Palette

| Role | Hex | Notes |
|---|---|---|
| editor bg | `#121314` | |
| chrome bg | `#191a1b` | sidebar, status, panel, inactive tabs |
| menu bg | `#202122` | |
| accent | `#3994bc` | cyan-blue |
| keyword | `#FF7B72` | red — `if`, `for`, `return`, `use` |
| function | `#D2A8FF` | purple |
| type | `#4EC9B0` | teal-green — also used for modules |
| constant | `#79C0FF` | light blue — enum members, numbers, booleans |
| macro | `#48a0c7` | darker blue — `println!`, `sc!` |
| string | `#A5D6FF` | |
| escape / `{}` | `#FF7B72` | red |
| comment | `#8B949E` | gray-blue, italic |
| param / decorator | `#FFA657` | orange |
| tag (HTML) | `#7EE787` | |

## Credits

- Original colorscheme by [D0nw0r/dark2026.nvim](https://github.com/D0nw0r/dark2026.nvim)

## License

MIT — see `LICENSE`.
