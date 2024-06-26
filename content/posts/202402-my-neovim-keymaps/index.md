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
| `<ESC>`      | Normal            | Clear search highlights                     |
| `<C-a>`      | Normal            | Select all                                  |
| `+`          | Normal            | Increment number under cursor               |
| `-`          | Normal            | Decrement number under cursor               |
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
| `<leader>sm` | Normal | Maximize/Minimize a split window        |
| `<leader>sx` | Normal | Close current slit window               |
| `<leader>se` | Normal | Make split windows equal width & height |
| `<Up>`       | Normal | Increase window height                  |
| `<Down>`     | Normal | Decrease window height                  |
| `<Right>`    | Normal | Increase window width                   |
| `<Left>`     | Normal | Decrease window width                   |

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
| `<leader>fe` | Normal | Toggle mini.files Explorer               |

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
| `]h`   | Normal | Jump to next git hunk start                       |
| `]t`   | Normal | Jump to next todo comment                         |
| `[f`   | Normal | Jump to previous function call start              |
| `[m`   | Normal | Jump to previous method/function definition start |
| `[c`   | Normal | Jump to previous class start                      |
| `[i`   | Normal | Jump to previous conditional start                |
| `[l`   | Normal | Jump to previous loop start                       |
| `[h`   | Normal | Jump to previous git hunk end                     |
| `[t`   | Normal | Jump to previous todo comment                     |

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
| `ih`   | Normal & Visual | Select git hunk                                   |

{{</table>}}

## Fuzzy Search Keybinds

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                             |
| ------------ | ------ | --------------------------------------- |
| `<leader>ff` | Normal | Fuzzy find files in cwd                 |
| `<leader>f.` | Normal | Fuzzy find recent files                 |
| `<leader>fs` | Normal | Find strings in cwd                     |
| `<leader>fc` | Normal | Find string under cursor in cwd         |
| `<leader>fr` | Normal | Resume Search                           |
| `<leader>fh` | Normal | Fuzzy find files in harpoon marked list |
| `<leader>ft` | Normal | Fuzzy find todos                        |
| `<leader>fn` | Normal | Fuzzy find neovim config files          |
| `<leader>/`  | Normal | Fuzzily search in current buffer        |
| `<leader>s/` | Normal | Find string in open files               |

{{</table>}}

## Harpoon Keybinds

{{<table "table table-striped table-bordered">}}

| Keymap      | Mode   | Description                                |
| ----------- | ------ | ------------------------------------------ |
| `<leader>a` | Normal | Add current buffer to harpoon marked list  |
| `<leader>h` | Normal | Toggle open/close harpoon marked list menu |
| `<C-n>`     | Normal | Go to next file on harpoon marked list     |
| `<C-p>`     | Normal | Go to previous file on harpoon marked list |
| `<leader>1` | Normal | Go to first file on harpoon marked list    |
| `<leader>2` | Normal | Go to second file on harpoon marked list   |
| `<leader>3` | Normal | Go to third file on harpoon marked list    |
| `<leader>4` | Normal | Go to fourth file on harpoon marked list   |

{{</table>}}

## Wakatime Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description              |
| ------------ | ------ | ------------------------ |
| `<leader>ct` | Normal | Echo today's coding time |

{{</table>}}

## Auto Session Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                           |
| ------------ | ------ | ------------------------------------- |
| `<leader>wr` | Normal | Restore session for current directory |
| `<leader>ws` | Normal | Save current session                  |

{{</table>}}

## Code Runner Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description        |
| ------------ | ------ | ------------------ |
| `<leader>rf` | Normal | Toggle run file    |
| `<leader>rp` | Normal | Toggle run project |

{{</table>}}

## Code Comments Keymaps

- I use the default keymaps in `Comment.nvim`. To learn how to use them, check out their [usage guide](https://github.com/numToStr/Comment.nvim/#-usage).

## Delimiter Pairs Keymaps

- For swift manipulation of delimiter pairs(quotes, braces, etc), I rely on the default keymaps from `mini.surround`. Explore their [usage guide](https://github.com/echasnovski/mini.nvim/blob/main/readmes/mini-surround.md#features) for insights into the diverse keymaps available.

## Code Completion

{{<table "table table-striped table-bordered">}}

| Keymap  | Mode   | Description                                |
| ------- | ------ | ------------------------------------------ |
| `<C-k>` | Insert | Previous suggestion                        |
| `<C-j>` | Insert | Next suggestion                            |
| `<C-b>` | Insert | Scroll up                                  |
| `<C-f>` | Insert | Scroll down                                |
| `<C-c>` | Insert | Show completion suggestions                |
| `<C-e>` | Insert | Close completion window/menu               |
| `<C-y>` | Insert | Select suggestion                          |
| `<C-n>` | Insert | Move to next snippet expansion option      |
| `<C-p>` | Insert | Move to previous snippet expansion options |

{{</table>}}

## Language Server Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode            | Description                                           |
| ------------ | --------------- | ----------------------------------------------------- |
| `gR`         | Normal          | Show references and definition                        |
| `gD`         | Normal          | Go to declaration                                     |
| `gd`         | Normal          | Show lsp definitions                                  |
| `gi`         | Normal          | Show lsp implementations                              |
| `gt`         | Normal          | Show lsp type definitions                             |
| `<leader>ca` | Normal & Visual | See available code actions                            |
| `<leader>rn` | Normal          | Smart rename                                          |
| `<leader>D`  | Normal          | Show diagnostics for file                             |
| `<leader>d`  | Normal          | Show diagnostics for line                             |
| `<leader>[d` | Normal          | Jump to previous diagnostic in buffer                 |
| `<leader>]d` | Normal          | Jump to next diagnostic in buffer                     |
| `<leader>K`  | Normal          | Show documentation for what is under cursor           |
| `<leader>rs` | Normal          | Restart lsp                                           |
| `dS`         | Normal          | Show LSP document symbols (variables, functions, etc) |
| `wS`         | Normal          | Show LSP workspace symbols                            |

{{</table>}}

## Trouble Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                        |
| ------------ | ------ | ---------------------------------- |
| `<leader>xx` | Normal | Toggle trouble list                |
| `<leader>xw` | Normal | Open trouble workspace diagnostics |
| `<leader>xd` | Normal | Open trouble document diagnostics  |
| `<leader>xq` | Normal | Open trouble quickfix list         |
| `<leader>xl` | Normal | Open trouble location list         |
| `<leader>xt` | Normal | Open todos in trouble              |

{{</table>}}

## Debugging Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                                |
| ------------ | ------ | ------------------------------------------ |
| `<leader>db` | Normal | Toggle breaking point on line under cursor |
| `<leader>dC` | Normal | Clear breakpoints                          |
| `<leader>ds` | Normal | Start debugging session                    |
| `<leader>dc` | Normal | Continue                                   |
| `<leader>do` | Normal | Step over                                  |
| `<leader>di` | Normal | Step into                                  |
| `<leader>dO` | Normal | Step out                                   |
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

| Keymap       | Mode   | Description                      |
| ------------ | ------ | -------------------------------- |
| `<leader>lt` | Normal | Trigger linting for current file |

{{</table>}}

## Markdown Preview Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                          |
| ------------- | ------ | ------------------------------------ |
| `<leader>mdp` | Normal | Start markdown preview (Browser tab) |
| `<leader>mdx` | Normal | Stop markdown preview                |

{{</table>}}

## Live Server Keymaps

- Live server is used to live reload HTML, CSS, and JavaScript files inside neovim

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description        |
| ------------ | ------ | ------------------ |
| `<leader>ls` | Normal | Toggle Live Server |

{{</table>}}

## Git Keymaps

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode            | Description                                                   |
| ------------- | --------------- | ------------------------------------------------------------- |
| `<leader>gi`  | Normal          | Git init                                                      |
| `<leader>gab` | Normal          | Stage current buffer                                          |
| `<leader>gub` | Normal          | Unstage current buffer                                        |
| `<leader>gac` | Normal & Visual | Stage selected hunk or hunk under cursor                      |
| `<leader>guc` | Normal          | Undo recent hunk stage                                        |
| `<leader>grc` | Normal & Visual | Reset selected hunk or hunk under cursor                      |
| `<leader>gbh` | Normal          | Open git blame                                                |
| `<leader>gbt` | Normal          | Toggle git blame on line under cursor                         |
| `<leader>gcp` | Normal          | Preview a hunk                                                |
| `<leader>gD`  | Normal          | Toggle deleted hunks                                          |
| `<leader>gw`  | Normal          | Save and stage current buffer in WT, checkout buffer in index |
| `<leader>gm`  | Normal          | Rename and stage current buffer                               |
| `<leader>gx`  | Normal          | Reset local changes in current buffer                         |
| `<leader>gs`  | Normal          | Toggle open/close of status tab                               |
| `<leader>gd`  | Normal          | Toggle open/close of diff tab                                 |
| `<leader>gg`  | Normal          | Open git graph                                                |
| `<leader>gou` | Normal          | Open git object in browser at upstream hosting provider       |

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
| `<leader>gzl` | Normal | List all the stash                                           |
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
| `<leader>gRh` | Normal | Hard reset the last commit               |
| `<leader>grk` | Normal | Populate reset with count from HEAD      |
| `<leader>gRk` | Normal | Populate hard reset with count from HEAD |
| `<leader>grO` | Normal | Populate git reset                       |

{{</table>}}

### Remote

{{<table "table table-striped table-bordered">}}

| Keymap        | Mode   | Description                    |
| ------------- | ------ | ------------------------------ |
| `<leader>gps` | Normal | Git push                       |
| `<leader>gPs` | Normal | Git force push                 |
| `<leader>gpl` | Normal | Git pull                       |
| `<leader>gPl` | Normal | Git force pull                 |
| `<leader>gpo` | Normal | Git push -u origin main        |
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

| Keymap               | Mode   | Description                                           |
| -------------------- | ------ | ----------------------------------------------------- |
| `j`, `<Down>`        | Normal | Move cursor to next file entry                        |
| `k`, `<Up>`          | Normal | Move cursor to next file entry                        |
| `o`, `<2-LeftMouse>` | Normal | Select current entry                                  |
| `s`                  | Normal | Stage/unstage selected entry                          |
| `S`                  | Normal | Stage all entries                                     |
| `U`                  | Normal | Unstage all entries                                   |
| `X`                  | Normal | Restore entry to state on left side                   |
| `R`                  | Normal | Update stats and entries on file list                 |
| `<S-Up>`             | Normal | Scroll up                                             |
| `<S-Down>`           | Normal | Scroll down                                           |
| `<C-j>`              | Normal | Open diff for next entry                              |
| `<C-k>`              | Normal | Open diff for previous entry                          |
| `gf`                 | Normal | Open file in a split window                           |
| `<CR>`               | Normal | Open file in a new tab                                |
| `i`                  | Normal | Toggle between list/tree views                        |
| `f`                  | Normal | Flatten empty subdirectories in tree listing style    |
| `<leader>e`          | Normal | Bring focus to the file panel                         |
| `<leader>cO`         | Normal | Choose OURS version of a confict for the whole file   |
| `<leader>cT`         | Normal | Choose THEIRS version of a confict for the whole file |
| `<leader>cB`         | Normal | Choose BASE version of a confict for the whole file   |
| `<leader>cA`         | Normal | Choose all versions of a confict for the whole file   |
| `dX`                 | Normal | Delete the confict region for the whole file          |

{{</table>}}

### diffview View Panel

{{<table "table table-striped table-bordered">}}

| Keymap       | Mode   | Description                                           |
| ------------ | ------ | ----------------------------------------------------- |
| `<C-j>`      | Normal | Open diff for next file                               |
| `<C-k>`      | Normal | Open diff for previous file                           |
| `<CR>`       | Normal | Open file in a previous tab                           |
| `<C-w><C-f>` | Normal | Open file in a split window                           |
| `<C-w>gf`    | Normal | Open file in a new tab                                |
| `<leader>e`  | Normal | Bring focus to the file panel                         |
| `<leader>b`  | Normal | Toggle file panel                                     |
| `<leader>co` | Normal | Choose OURS version of a confict                      |
| `<leader>ct` | Normal | Choose THEIRS version of a confict                    |
| `<leader>cb` | Normal | Choose BASE version of a confict                      |
| `<leader>ca` | Normal | Choose all versions of a confict                      |
| `dx`         | Normal | Delete the conflict region                            |
| `<leader>cO` | Normal | Choose OURS version of a confict for the whole file   |
| `<leader>cT` | Normal | Choose THEIRS version of a confict for the whole file |
| `<leader>cB` | Normal | Choose BASE version of a confict for the whole file   |
| `<leader>cA` | Normal | Choose all versions of a confict for the whole file   |
| `dX`         | Normal | Delete the conflict region for the whole file         |

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
