+++
title = "My Neovim Keymaps"
date = 2024-02-17T23:36:25+03:00
draft = false
tags = ["neovim"]
series = ["My Neovim Configuration"]
series_order = 2
+++

In this article, I'll be sharing the keymaps I've configured within my Neovim setup to enhance simplicity and improve efficiency.

## Basic Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode              | Description                                 |
| ------------ | ----------------- | ------------------------------------------- |
| `<Space>`    | N/A               | Leader key                                  |
| `jk`         | Insert            | Exit insert mode                            |
| `<leader>nh` | Normal            | Clear search highlights                     |
| `<leader>+`  | Normal            | Increment number under cursor               |
| `<leader>-`  | Normal            | Decrement number under cursor               |
| `<leader>rw` | Normal            | Toggle Find & Replace                       |
| `<leader>rc` | Normal            | Toggle Find & Replace for word under cursor |
| `<C-z>`      | Normal & Terminal | Toggle FTerm terminal                       |

{{</table>}}

## Window Management Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                             |
| ------------ | ------ | --------------------------------------- |
| `<leader>sv` | Normal | Split window vertically                 |
| `<leader>sh` | Normal | Split window horizontally               |
| `<leader>se` | Normal | Make split windows equal width & height |
| `<leader>sm` | Normal | Maximize/Minimize a split window        |
| `<leader>sx` | Normal | Close current slit window               |

{{</table>}}

## Tab Management Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                    |
| ------------ | ------ | ------------------------------ |
| `<leader>to` | Normal | Open new tab                   |
| `<leader>tx` | Normal | Close current tab              |
| `<leader>tn` | Normal | Go to next tab                 |
| `<leader>tp` | Normal | Go to previous tab             |
| `<leader>tf` | Normal | Move current buffer to new tab |

{{</table>}}

## Window Navigation Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap  | Mode   | Description                            |
| ------- | ------ | -------------------------------------- |
| `<C-h>` | Normal | Move cursor to the window on the left  |
| `<C-j>` | Normal | Move cursor to the window below        |
| `<C-k>` | Normal | Move cursor to the window above        |
| `<C-l>` | Normal | Move cursor to the window on the right |

{{</table>}}

- This works with my Tmux confnguration, so be sure to check it out as well. Link provided on the [Recommendations](#recommendations) section.

## File Explorer Keymaps

- Explore the various keymaps of `nvim-tree` by opening the `QUICKSTART HELP` with `g?` while the cursor is on the explorer split. Close the help menu using `q` key.

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                              |
| ------------ | ------ | ---------------------------------------- |
| `<leader>ee` | Normal | Toggle file explorer                     |
| `<leader>ef` | Normal | Toggle file explorer on the current file |
| `<leader>ec` | Normal | Collapse file explorer                   |
| `<leader>er` | Normal | Refresh file explorer                    |

{{</table>}}

## Navigation within Code

{{<table "table table-striped table-bordered">}}

| Keymap | Mode   | Description                                       |
| ------ | ------ | ------------------------------------------------- |
| `]f`   | Normal | Jump to next function call start                  |
| `]m`   | Normal | Jump to next method/function definition start     |
| `]c`   | Normal | Jump to next class start                          |
| `]i`   | Normal | Jump to next conditional start                    |
| `]l`   | Normal | Jump to next loop start                           |
| `[f`   | Normal | Jump to previous function call start              |
| `[m`   | Normal | Jump to previous method/function definition start |
| `[c`   | Normal | Jump to previous class start                      |
| `[i`   | Normal | Jump to previous conditional start                |
| `[l`   | Normal | Jump to previous loop start                       |

{{</table>}}

{{<table "table table-striped table-bordered">}}

| Keymap | Mode   | Description                                     |
| ------ | ------ | ----------------------------------------------- |
| `]F`   | Normal | Jump to next function call end                  |
| `]M`   | Normal | Jump to next method/function definition end     |
| `]C`   | Normal | Jump to next class end                          |
| `]I`   | Normal | Jump to next conditional end                    |
| `]L`   | Normal | Jump to next loop end                           |
| `[F`   | Normal | Jump to previous function call end              |
| `[M`   | Normal | Jump to previous method/function definition end |
| `[C`   | Normal | Jump to previous class end                      |
| `[I`   | Normal | Jump to previous conditional end                |
| `[L`   | Normal | Jump to previous loop end                       |

{{</table>}}

{{<table "table table-striped table-bordered">}}

| Keymap | Mode   | Description        |
| ------ | ------ | ------------------ |
| `]s`   | Normal | Jump to next scope |
| `]z`   | Normal | Jump to next fold  |

{{</table>}}

## Swap Text Objects in Code

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                               |
| ------------ | ------ | ----------------------------------------- |
| `<leader>na` | Normal | Swap parameter/argument with the next     |
| `<leader>nm` | Normal | Swap function with the next               |
| `<leader>pa` | Normal | Swap parameter/argument with the previous |
| `<leader>pm` | Normal | Swap function with the previous           |

{{</table>}}

## Manipulate Text Objects in Code

In `Normal` mode, you can use the following key bindings prefixed with operations like `d`, `c`, or `y` to interact with text objects. Here are some examples:

- `daa`: Delete the outer part of an argument.
- `caa`: Change the outer part of an argument.
- `yaa`: Yank the outer part of an argument.

And so on.

{{<table "table table-striped table-bordered">}}

| Keymap | Mode            | Description                                       |
| ------ | --------------- | ------------------------------------------------- |
| `a=`   | Normal & Visual | Select outer part of an assignment                |
| `i=`   | Normal & Visual | Select inner part of an assignment                |
| `l=`   | Normal & Visual | Select left hand side of an assignment            |
| `r=`   | Normal & Visual | Select right hand side of an assignment           |
| `aa`   | Normal & Visual | Select outer part of a parameter/argument         |
| `ia`   | Normal & Visual | Select inner part of a parameter/argument         |
| `ai`   | Normal & Visual | Select outer part of a condition                  |
| `ii`   | Normal & Visual | Select inner part of a condition                  |
| `al`   | Normal & Visual | Select outer part of a loop                       |
| `il`   | Normal & Visual | Select inner part of a loop                       |
| `af`   | Normal & Visual | Select outer part of a function call              |
| `if`   | Normal & Visual | Select inner part of a function call              |
| `am`   | Normal & Visual | Select outer part of a method/function definition |
| `im`   | Normal & Visual | Select inner part of a method/function definition |
| `ac`   | Normal & Visual | Select outer part of a class                      |
| `ic`   | Normal & Visual | Select inner part of a class                      |

{{</table>}}

## Fuzzy Search Keybinds

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                     |
| ------------ | ------ | ------------------------------- |
| `<leader>ff` | Normal | Fuzzy find files in cwd         |
| `<leader>fr` | Normal | Fuzzy find recent files         |
| `<leader>fs` | Normal | Find strings in cwd             |
| `<leader>fc` | Normal | Find string under cursor in cwd |

{{</table>}}

## Code Comments Keymaps

- I use the default keymaps in `Comment.nvim`. To learn how to use them, check out their [usage guide](https://github.com/numToStr/Comment.nvim/#-usage).

## Delimiter Pairs Keymaps

- For swift manipulation of delimiter pairs, I rely on the default keymaps from `nvim-surround`. Explore their [usage guide](https://github.com/kylechui/nvim-surround?tab=readme-ov-file#rocket-usage) for insights into the diverse keymaps available.

## Code Completion

{{<table "table table-striped table-bordered">}}

| Keymap      | Mode   | Description                  |
| ----------- | ------ | ---------------------------- |
| `<C-k>`     | Insert | Previous suggestion          |
| `<C-j>`     | Insert | Next suggestion              |
| `<C-b>`     | Insert | Scroll up                    |
| `<C-f>`     | Insert | Scroll down                  |
| `<C-Space>` | Insert | Show completion suggestions  |
| `<C-e>`     | Insert | Close completion window/menu |
| `<CR>`      | Insert | Select suggestion            |

{{</table>}}

## Language Server Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode            | Description                                 |
| ------------ | --------------- | ------------------------------------------- |
| `gR`         | Normal          | Show references and definition              |
| `gD`         | Normal          | Go to declaration                           |
| `gd`         | Normal          | Show lsp definitions                        |
| `gi`         | Normal          | Show lsp implementations                    |
| `gt`         | Normal          | Show lsp type definitions                   |
| `<leader>ca` | Normal & Visual | See available code actions                  |
| `<leader>rn` | Normal          | Smart rename                                |
| `<leader>D`  | Normal          | Show diagnostics for file                   |
| `<leader>d`  | Normal          | Show diagnostics for line                   |
| `<leader>[d` | Normal          | Jump to previous diagnostic in buffer       |
| `<leader>]d` | Normal          | Jump to next diagnostic in buffer           |
| `<leader>K`  | Normal          | Show documentation for what is under cursor |
| `<leader>rs` | Normal          | Restart lsp                                 |

{{</table>}}

## Debugging Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                                |
| ------------ | ------ | ------------------------------------------ |
| `<leader>db` | Normal | Toggle breaking point on line under cursor |
| `<leader>dC` | Normal | Clear breakpoints                          |
| `<leader>ds` | Normal | Start debugging session                    |
| `<leader>dc` | Normal | Continue                                   |
| `<leader>dn` | Normal | Step over                                  |
| `<leader>di` | Normal | Step into                                  |
| `<leader>do` | Normal | Step out                                   |
| `<leader>de` | Normal | Close debugger and end debugging session   |
| `<leader>dc` | Normal | Continue                                   |

{{</table>}}

## Formatting Keymaps

- Automatic formatting takes effect upon saving the current buffer, provided you have a formatter for the language in use.

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode            | Description           |
| ------------ | --------------- | --------------------- |
| `<leader>mp` | Normal          | Format file           |
| `<leader>mp` | Normal & Visual | Format selected range |

{{</table>}}

## Linting Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap      | Mode   | Description                      |
| ----------- | ------ | -------------------------------- |
| `<leader>l` | Normal | Trigger linting for current file |

{{</table>}}

## Markdown Preview Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                          |
| ------------- | ------ | ------------------------------------ |
| `<leader>mdp` | Normal | Start markdown preview (Browser tab) |
| `<leader>mdx` | Normal | Stop markdown preview                |

{{</table>}}

## Git Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                                                   |
| ------------ | ------ | ------------------------------------------------------------- |
| `<leader>gi` | Normal | Git init                                                      |
| `<leader>ga` | Normal | Stage current buffer                                          |
| `<leader>gw` | Normal | Save and stage current buffer in WT, checkout buffer in index |
| `<leader>gm` | Normal | Rename and stage current buffer                               |
| `<leader>gs` | Normal | Toggle open/close of status tab                               |
| `<leader>gd` | Normal | Toggle open/close of diff tab                                 |
| `<leader>gg` | Normal | Open git graph                                                |

{{</table>}}

### Commits

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                           |
| ------------- | ------ | ----------------------------------------------------- |
| `<leader>gcc` | Normal | Populate git commit with message flag on command line |
| `<leader>gca` | Normal | Amend the last commit                                 |
| `<leader>gcm` | Normal | populate git commit on command line                   |

{{</table>}}

### Branches

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                           |
| ------------- | ------ | ----------------------------------------------------- |
| `<leader>gbl` | Normal | List all branches                                     |
| `<leader>gbv` | Normal | List all branches with their remote tracking branches |
| `<leader>gbo` | Normal | Populate git branch on command line                   |
| `<leader>gba` | Normal | Populate create branch and switch to it               |
| `<leader>gbr` | Normal | Populate rename branch                                |
| `<leader>gbd` | Normal | Populate delete branch                                |
| `<leader>gbD` | Normal | Populate force delete branch                          |
| `<leader>gco` | Normal | Populate git checkout                                 |

{{</table>}}

### Stash

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                                  |
| ------------- | ------ | ------------------------------------------------------------ |
| `<leader>gzz` | Normal | Push stash (includes untracked files) from both WT and index |
| `<leader>gzw` | Normal | Push stash (includes untracked files) from WT only           |
| `<leader>gza` | Normal | Apply top most stash                                         |
| `<leader>gzA` | Normal | Populate apply stash                                         |
| `<leader>gzp` | Normal | Pop top most stash                                           |
| `<leader>gzP` | Normal | Populate pop stash                                           |
| `<leader>gzd` | Normal | Drop top most stash                                          |
| `<leader>gzD` | Normal | Populate drop stash                                          |
| `<leader>gzo` | Normal | Populate git stash                                           |

{{</table>}}

### Merge

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                                     |
| ------------- | ------ | --------------------------------------------------------------- |
| `<leader>gmo` | Normal | Populate git merge                                              |
| `<leader>gmt` | Normal | Open merge tool _consider using diffview for solving conflicts_ |
| `<leader>gmr` | Normal | Continue merging                                                |
| `<leader>gmx` | Normal | Abort merging                                                   |

{{</table>}}

### Rebase

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                      |
| ------------- | ------ | ------------------------------------------------ |
| `<leader>gri` | Normal | Populate interactive rebase                      |
| `<leader>grn` | Normal | Populate interactive rebase with count from HEAD |
| `<leader>grr` | Normal | Continue with current rebase                     |
| `<leader>grx` | Normal | Abort current rebase                             |
| `<leader>gre` | Normal | Edit todo list of current rebase                 |
| `<leader>gro` | Normal | Populate git rebase                              |

{{</table>}}

### Cherry Pick

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description               |
| ------------- | ------ | ------------------------- |
| `<leader>gyi` | Normal | Populate git cherry-pick  |
| `<leader>gyr` | Normal | Continue with cherry-pick |
| `<leader>gyx` | Normal | Abort cherry-pick         |

{{</table>}}

### Reset

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                              |
| ------------- | ------ | ---------------------------------------- |
| `<leader>grh` | Normal | Reset the last commit                    |
| `<leader>gRr` | Normal | Hard reset the last commit               |
| `<leader>gri` | Normal | Populate reset with count from HEAD      |
| `<leader>gRi` | Normal | Populate hard reset with count from HEAD |
| `<leader>grO` | Normal | Populate git reset                       |

{{</table>}}

### Remote

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                    |
| ------------- | ------ | ------------------------------ |
| `<leader>gps` | Normal | Git push                       |
| `<leader>gPs` | Normal | Git force push                 |
| `<leader>gpl` | Normal | Git pull                       |
| `<leader>gPL` | Normal | Git force pull                 |
| `<leader>gpu` | Normal | Populate git push set upstream |
| `<leader>gra` | Normal | Populate add remote            |
| `<leader>grd` | Normal | Populate remove remote         |
| `<leader>grl` | Normal | List all remotes               |
| `<leader>gor` | Normal | Populate git remote            |

{{</table>}}

## Git diffview

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                                          |
| ------------- | ------ | ---------------------------------------------------- |
| `<leader>gd`  | Normal | Toggle open/close diffview tab                       |
| `<leader>gfh` | Normal | Toggle open/close file history of current buffer tab |
| `<leader>gh`  | Normal | Toggle open/close all commits/files history tab      |
| `<leader>gR`  | Normal | Toggle open/close diff of HEAD and main branch       |

{{</table>}}

### diffview File Panel

{{<table "table table-striped table-bordered">}}

| Keymap               | Mode   | Description                                        |
| -------------------- | ------ | -------------------------------------------------- |
| `j`, `<Down>`        | Normal | Move cursor to next file entry                     |
| `k`, `<Up>`          | Normal | Move cursor to next file entry                     |
| `o`, `<2-LeftMouse>` | Normal | Select current entry                               |
| `-`                  | Normal | Stage/unstage selected entry                       |
| `S`                  | Normal | Stage all entries                                  |
| `U`                  | Normal | Unstage all entries                                |
| `X`                  | Normal | Restore entry to state on left side                |
| `R`                  | Normal | Update stats and entries on file list              |
| `<S-Up>`             | Normal | Scroll up                                          |
| `<S-Down>`           | Normal | Scroll down                                        |
| `<C-j>`              | Normal | Open diff for next entry                           |
| `<C-k>`              | Normal | Open diff for previous entry                       |
| `gf`                 | Normal | Open file in a split window                        |
| `<CR>`               | Normal | Open file in a new tab                             |
| `i`                  | Normal | Toggle between list/tree views                     |
| `f`                  | Normal | Flatten empty subdirectories in tree listing style |
| `<leader>e`          | Normal | Bring focus to the file panel                      |

{{</table>}}

### diffview View Panel

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                   |
| ------------ | ------ | ----------------------------- |
| `<C-j>`      | Normal | Open diff for next file       |
| `<C-k>`      | Normal | Open diff for previous file   |
| `<CR>`       | Normal | Open file in a previous tab   |
| `<C-w><C-f>` | Normal | Open file in a split window   |
| `<C-w>gf`    | Normal | Open file in a new tab        |
| `<leader>e`  | Normal | Bring focus to the file panel |
| `<leader>b`  | Normal | Toggle file panel             |

{{</table>}}

### diffview File History Panel

{{<table "table table-striped table-bordered">}}

| Keymap                       | Mode   | Description                           |
| ---------------------------- | ------ | ------------------------------------- |
| `g!`                         | Normal | Open option panel                     |
| `<C-A-d>`                    | Normal | Open entry under cursor in a diffview |
| `zR`                         | Normal | Open all folds                        |
| `zM`                         | Normal | Close all folds                       |
| `j`, `<Down>`                | Normal | Move cursor to next entry             |
| `k`, `<Up>`                  | Normal | Move cursor to previous entry         |
| `o`, `<CR>`, `<2-LeftMouse>` | Normal | Select entry                          |
| `<C-j>`                      | Normal | Select next entry                     |
| `<C-k>`                      | Normal | Select previous entry                 |
| `gf`                         | Normal | Go to file                            |
| `<C-w><C-f>`                 | Normal | Open file in a split window           |
| `<C-w>gf`                    | Normal | Open file in a new tab                |
| `<leader>e`                  | Normal | Bring focus to the file panel         |
| `<leader>b`                  | Normal | Toggle file panel                     |

{{</table>}}
