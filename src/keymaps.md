# Keymaps Documentation

This page lists the non-negotiable keymaps from `keymaps.lua`: P0 covers daily survival commands, and P1 covers important workflow accelerators. Minor toggles, legacy duplicates, and low-frequency helpers are intentionally omitted.

## P0 Keymaps

### Editing and Buffers

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<leader>w` | `:w` | Save the current file |
| Normal | `<leader>c` | `:q` | Close the current window |
| Normal | `<leader>q` | `:bd` | Delete the current buffer |
| Normal | `<space>[` | `:bprev` | Go to the previous buffer |
| Normal | `<space>]` | `:bnext` | Go to the next buffer |
| Normal | `<Esc><Esc>` | `:noh` | Clear search highlighting |
| Insert | `<C-l>` | `<Esc>` | Leave Insert mode |
| Visual | `<C-l>` | `<Esc>` | Leave Visual mode |

### Files and Project Search

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<leader>ff` | `Telescope find_files` | Find files in the project |
| Normal | `<leader>fg` | `Telescope live_grep` | Search text across the project |
| Normal | `<leader>fb` | `Telescope buffers` | Switch between open buffers |
| Normal | `<C-t>` | `Neotree toggle` | Toggle the file tree |

### LSP and Code Navigation

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `gd` | `vim.lsp.buf.definition` | Go to definition |
| Normal | `gD` | `vim.lsp.buf.declaration` | Go to declaration |
| Normal | `gi` | `vim.lsp.buf.implementation` | Go to implementation |
| Normal | `gr` | `vim.lsp.buf.references` | List references |
| Normal | `K` | `Lspsaga hover_doc` | Show hover documentation |
| Normal | `<C-k>` | `vim.lsp.buf.signature_help` | Show signature help |
| Normal | `<space>rn` | `vim.lsp.buf.rename` | Rename symbol |
| Normal, Visual | `zi` | `vim.lsp.buf.code_action` | Open code actions |
| Normal | `<space>f` | `vim.lsp.buf.format` | Format the current buffer |
| Visual | `<space>qf` | `vim.lsp.buf.range_formatting` | Format the selected range |
| Normal | `zj` | `vim.diagnostic.goto_prev` | Go to previous diagnostic |
| Normal | `zk` | `vim.diagnostic.goto_next` | Go to next diagnostic |
| Normal | `zo` | `Lspsaga show_line_diagnostics` | Show diagnostics for the current line |

### Git

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<leader>g` | `:G` | Open Fugitive Git status |
| Normal | `<space>gd` | `Gitsigns diffthis HEAD~1` | Diff current file against previous commit |
| Normal | `<space>gj` | `Gitsigns next_hunk` | Go to next Git hunk |
| Normal | `<space>gk` | `Gitsigns prev_hunk` | Go to previous Git hunk |
| Normal | `<space>gs` | `Gitsigns stage_hunk` | Stage current hunk |
| Normal | `<space>gu` | `Gitsigns undo_stage_hunk` | Undo staged hunk |

### Debugging

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<leader>db` | `dap.toggle_breakpoint()` | Toggle breakpoint |
| Normal | `<leader>dc` | `dap.continue()` | Start or continue debugging |
| Normal | `<leader>di` | `dap.step_into()` | Step into |
| Normal | `<leader>do` | `dap.step_over()` | Step over |
| Normal | `<Leader>dk` | `dap.step_out()` | Step out |
| Normal | `<leader>dt` | `dapui.toggle()` | Toggle DAP UI |
| Normal | `<leader>dq` | `dap.terminate()` | Stop debugging |

## P1 Keymaps

### Navigation and Layout

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<space>aa` | `harpoon.mark.add_file()` | Add current file to Harpoon |
| Normal | `<space>at` | `harpoon.ui.toggle_quick_menu()` | Open Harpoon quick menu |
| Normal | `<space>aw` | `harpoon.ui.nav_next()` | Go to next Harpoon file |
| Normal | `<space>as` | `harpoon.ui.nav_prev()` | Go to previous Harpoon file |
| Normal | `<leader>h` | `vsplit` | Split window to the left |
| Normal | `<leader>j` | `split` then move down | Split window below |
| Normal | `<leader>k` | `split` | Split window above/current |
| Normal | `<leader>l` | `vsplit` then move right | Split window to the right |
| Normal | `<space><Tab>` | `Outline` | Toggle symbols outline |

### Tests

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `<leader>tn` | `neotest.run.run()` | Run nearest test |
| Normal | `<leader>tt` | `neotest.run.run(current file)` | Run the current test file |
| Normal | `<leader>td` | `neotest.run.run({ strategy = "dap" })` | Debug nearest test |
| Normal | `<leader>ts` | `neotest.run.stop()` | Stop nearest test run |
| Normal | `<leader>to` | `neotest.output.open({ enter = true })` | Open test output |
| Normal | `<leader>tp` | `neotest.output_panel.toggle()` | Toggle test output panel |
| Normal | `<leader>tv` | `neotest.summary.toggle()` | Toggle test summary |

### AI Assistance

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Insert | `<C-J>` | `copilot#Accept()` | Accept Copilot suggestion |
| Normal | `<leader>ag` | `CodeCompanionChat` | Open CodeCompanion chat |
| Normal | `<leader>ah` | `CodeCompanionActions` | Open CodeCompanion actions |
| Normal | `<leader>i` | `ChatGPT` | Open ChatGPT |

### Supporting Tools

| Mode | Key | Action | Description |
| --- | --- | --- | --- |
| Normal | `U` | `UndotreeToggle` | Toggle undo history |
| Normal, Visual | `ga` | `EasyAlign` | Align text |
| Normal | `<leader>xz` | `vim.lsp.inlay_hint.enable(...)` | Toggle inlay hints |
