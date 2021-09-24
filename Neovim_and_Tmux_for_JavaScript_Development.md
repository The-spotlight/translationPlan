# Neovim and Tmux for JavaScript Development

https://elijahmanor.com/blog/neovim-tmux

The following is a quick 2 minute tour using Neovim and Tmux to navigate around multiple projects and files. I show off a few handy Neovim plugins that I regularly use along with native LSP features that I've installed for JavaScript and TypeScript development.

[](#frontend-masters-vim-course)FrontEnd Masters VIM Course
-----------------------------------------------------------

Back in May 2021, I completed the [VIM Fundamentals](https://frontendmasters.com/courses/vim-fundamentals/) (4 hours, 14 minutes) course on FrontEnd Masters by [@ThePrimeagen](https://twitter.com/theprimeagen). The energy and the depth of knowledge of the material were great. This course started my journey to use Neovim as my primary editor for both work and personal use.

[![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTY3NSIgaGVpZ2h0PSI4MTIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)](https://frontendmasters.com/courses/vim-fundamentals/)[![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)](https://frontendmasters.com/courses/vim-fundamentals/)

[](#what-is-neovim)What is Neovim?
----------------------------------

[Neovim](https://neovim.io/) started as a fork of Vim v7. Some of the interesting differences in Neovim are its built-in LSP (Language Server Protocol) support and Lua as an embedded language, which is an alternative to Vimscript. There are [a lot more features](https://neovim.io/) you can check out on their website.

Interestingly enough, Neovim came in #1 in the Stackoverflow 2021 Developer Survey for the [Most Loved Collaboration Tool](https://neovim.io/)!

[![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTg2OCIgaGVpZ2h0PSI4NzQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-collaboration-tools)[![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-collaboration-tools)

Why is Neovim so loved? Well, in a recent podcast of [The Changlog - Episode #457](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-collaboration-tools) called **Why Neovim?**, [TJ DeVries](https://github.com/tjdevries) ([@TeejDeVries](https://twitter.com/TeejDeVries)) discusses with hosts [Jerod Santo](https://github.com/jerodsanto) ([@jerodsanto](https://twitter.com/jerodsanto)) and [Nick Nisi](https://nicknisi.com/) ([@nicknisi](https://twitter.com/nicknisi)) about the backstory and reasons why Neovim is pretty cool.

[](#setting-up-neovim-for-javascript)Setting Up Neovim for JavaScript
---------------------------------------------------------------------

### [](#installing-neovim)Installing Neovim

I personally use `brew` to install most of my apps, but if you don't use macOS (or prefer another method), there are lots of options to install on the main [Neovim wiki](https://github.com/neovim/neovim/wiki/Installing-Neovim#homebrew-on-macos-or-linux).

```
brew install neovim
```

> NOTE: My `<leader>` key is mapped to the `<space>` key (more accurately `let mapleader = " "`)

### [](#helpful-vim-plugins)Helpful Vim Plugins

There are several ways to managed vim plugins, but I've been using [vim-plug](https://changelog.com/podcast/457), and it suites my needs just fine. One feature that I learned about recently is that you can type `D` after you `PlugUpdate` and it'll show a detailed list of commits that were included in each plugin update.

#### [](#language-server-protocol)Language Server Protocol

![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQ0MCIgaGVpZ2h0PSI4MTAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

The LSP is what enables Neovim to have strong integration with your languages of choice. I use the [`typescript-language-server`](https://github.com/typescript-language-server/typescript-language-server), which is an implementation for TypeScript wrapping `tsserver`.

*   [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) - A collection of common configurations for Neovim's built-in Language Server Protocol
*   [nvim-compe](https://github.com/hrsh7th/nvim-cmp) - Auto-completion plugin for Neovim written in Lua
*   [lspsaga.nvim](https://github.com/glepnir/lspsaga.nvim) - A light-weight LSP plugin based on Neovim's LSP with a highly performant UI (code actions, hover docs, signature help, rename, preview definition, floating terminal, etc...)
*   [trouble.nvim](https://github.com/folke/trouble.nvim) - A pretty list for showing diagnostics, reference, telescope results, quickfix, and location lists to help you solve all the trouble your code is causing.

##### [](#common-commands)Common Commands

There are a lot of commands that you can invoke regarding LSP, but the following are some that I regularly use.

*   `gd` - Go to definition
*   `gf` - Go to file location
*   `K` - Show hover documentation
*   `<leader>ca` - Launch code actions

#### [](#file-management)File Management

![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQ0MCIgaGVpZ2h0PSI4MTAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

If I'm familiar with a code-base then a fuzzy file finder is great, but sometimes I like having a file-tree plugin to understand how files and folders relate to each-other. In addition, telescope provides may other ways to navigate (global grep, git status, etc...).

*   [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim) - A highly extendable fuzzy finder over lists. This can find files, live grep, manage buffers, search through git files, a file browser, change themes, and a lot more!
*   [telescope-fzf-native.nvim](https://github.com/nvim-telescope/telescope-fzf-native.nvim) - A telescope extension that uses `fzf` to override the file sorter
*   [nvim-tree.lua](https://github.com/kyazdani42/nvim-tree.lua) - A file explorer for Neovim written in Lua

##### [](#common-commands-1)Common Commands

There are many more built-in lists available in telescope (and others you can add via plugs or by yourself), but the following are the ones I use regularly.

*   `<leader>ff` - telescope find files across project
*   `<leader>fg` - telescope live grep across project
*   `<leader>fc` - telescope find by git status changed
*   `<leader>fs` - telescope navigate file system
*   `<leader>fb` - telescope switch between active buffers
*   `<C-n>` - toggle file tree (specific to `nvim-tree.lua`)

> NOTE: The above are custom remaps. You can take a peek at my [`init.vim`](https://github.com/elijahmanor/dotfiles/blob/master/nvim/.config/nvim/init.vim) from my dotfiles repo.

#### [](#status-line)Status Line

These plugins provide some nice style and additional features to Neovim. There are lots of choices to choose from, but these are the ones I've settled on for the time being.

*   [lualine.nvim](https://github.com/hoob3rt/lualine.nvim) - A blazing fast and easy to configure Neovim statusline written in Lua
*   [nvim-bufferline.lua](https://github.com/akinsho/nvim-bufferline.lua) - A snazzy buffer line for Neovim built using Lua
*   [nvim-web-devicons](https://github.com/kyazdani42/nvim-web-devicons) - A Lua port of vim-devicons that adds fancy icons to your plugins

#### [](#syntax-highlightning)Syntax Highlightning

I use `nvim-treesitter` for most of my sytnax highlighting needs. I do use `vim-jsx-pretty` to fill in some behavior gaps when using JSX, but that's about it. Two areas that I am lacking are support for `styled-components` and `mdx`.

*   [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) - Provide both a simple and easy way to use [tree-sitter](https://github.com/tree-sitter/tree-sitter) in Neovim. This provides basic functionality such as highlighting.
*   [vim-jsx-pretty](https://github.com/MaxMEllon/vim-jsx-pretty) - `nvim-treesitter` currently doesn't JSX indenting very well, so I use this plugin to help fill that gap.

#### [](#tim-pope-plugins)Tim Pope Plugins

[Tim Pope](https://github.com/tpope) ([@tpope](https://twitter.com/tpope)) has a vast amount of helpful and vim plugins that he has developed over the years. Here are a few that I use.

*   [vim-unimpaired](https://github.com/tpope/vim-unimpaired) - A handy plugin to provide a suite of mapping pairs for many common actions (navigating buffers, quicklist, and lots more).
*   [vim-surround](https://github.com/tpope/vim-surround) - A nice plugin to surround text (with parens, brackets, quotes, tags, etc...) or to replace or delete those delimeters.
*   [vim-commentary](https://github.com/tpope/vim-commentary) - Easily comment or uncomment code a line of code or the target of a motion.
*   [vim-repeat](https://github.com/tpope/vim-repeat) - This plugin enables other plugins to use the `.` command to repeat the last command.
*   [vim-sleuth](https://github.com/tpope/vim-sleuth) - This plugin automatically adjusts `shiftwidth` and `expandtab` based on the current file's settings or files of the same type.

#### [](#misc-plugins)Misc Plugins

![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQ0MCIgaGVpZ2h0PSI4MDkiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

The above picture shows the dashboard-nvim plugin. It's a friendlier splash-screen verses the one that comes native with Neovim. I've listed several other plugins that I find useful as well.

*   [dashboard-nvim](https://github.com/glepnir/dashboard-nvim) - A start dashboard for vim with a list of common commands
*   [gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim) - Super fast git decorations shown in the gutter implemented by Lua
*   [neoscroll.nvim](https://github.com/karb94/neoscroll.nvim) - A smooth scrolling Neovim plugin written in Lua. Scrolling shows up for `<C-u>`, `C-d>`, `<C-b>`, `<C-f>`, `<C-e>`, `zt`, `zz`, and `zb`
*   [nvim-colorizer.lua](https://github.com/norcalli/nvim-colorizer.lua) - A high-performance color highlighter for Neovim written in Lua
*   [nvim-autopairs](https://github.com/windwp/nvim-autopairs) - A powerful autopairs plugin for Neovim
*   ~[vim-highlightedyank](https://github.com/machakann/vim-highlightedyank) - Briefly highlight the yanged region~

> NOTE: jdhao ([@flying_unclecat](https://twitter.com/flying_unclecat)) reached out to me on [Twitter](flying_unclecat) and let me know that I no longer need the **vim-highlightedyank** plugin listed above. Neovim can now support that same behavior with [`vim.highlight.on_yank`](https://jdhao.github.io/2020/05/22/highlight_yank_region_nvim/#neovim-only)!

#### [](#theme)Theme

I primarily use the Dracula theme because it's available for both vim and tmux and I like the consistency and the color choices.

*   [dracula](https://github.com/dracula/vim) - A dark theme for Vim.

### [](#installing-neovim)Vim Learning Resources

There are some great free learning materials online for `vim`. A few videos that I really enjoyed are listed below:

*   [Onramp to Vim](https://thoughtbot.com/upcase/onramp-to-vim) taught by Ben Orenstein ([@r00k](https://twitter.com/r00k)) and [Chris Toomey](https://ctoomey.com/) ([@christoomey](https://twitter.com/christoomey)) and provided by [@thoughtbot](https://twitter.com/thoughtbot)
*   [Dive into Neovim](https://thoughtbot.com/upcase/dive-into-neovim) taught by Drew Neil and provided by [@thoughtbot](https://twitter.com/thoughtbot)
*   [Vimcasts](http://vimcasts.org/) taught by [Drew Neil](http://drewneil.com/) ([@nelstrom](https://twitter.com/nelstrom))
*   [Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0) taught by [Chris Toomey](https://ctoomey.com/) ([@christoomey](https://twitter.com/christoomey))
*   [Learning Vim in a Week](https://www.youtube.com/watch?v=_NUO4JEtkDw) taught by [Mike Coutermarsh](https://twitter.com/mscccc)
*   [How to Do 90% of What Plugins Do (With Just Vim)](https://www.youtube.com/watch?v=XA2WjJbmmoM) taught by Max Cantor
*   [Exploring Vim Series](https://www.barbarianmeetscoding.com/series/exploring-vim) and [5 Minutes Vim Series](https://www.barbarianmeetscoding.com/series/5-minutes-vim) written by [Jaime González García](https://www.barbarianmeetscoding.com/) ([@Vintharas](https://twitter.com/Vintharas))

on his blog!

### [](#helpful-vim-cheatsheets)Helpful Vim Cheatsheets

I've seen numverous Vim cheatsheets, but the following are a list that I found to be helpful.

*   [Vim cheatsheet](https://devhints.io/vim) by [devhints](https://devhints.io/)
*   [Dash Vim cheatsheet](https://kapeli.com/cheat_sheets/Vim.docset/Contents/Resources/Documents/index) by [Kapeli](https://twitter.com/kapeli) maker of [Dash](https://kapeli.com/dash)
*   [Vim Cheat Sheet](https://vim.rtorr.com/) by [Richard Torruellas](https://www.rtorr.com/) ([@richardiii](https://twitter.com/richardiii))
*   [Vim cheatsheet](https://quickref.me/vim) by [QuickRef.ME](https://quickref.me/)
*   A searchable [cheatsheet](https://github.com/sudormrfbin/cheatsheet.nvim) plugin for Neovim from within the editor using Telescope

### [](#social-resources)Social Resources

During my process of learning Vim and Neovim, I've followed the following individuals on Twitter, YouTube, and Twitch. They have been a wealth of knowledge and I continue to learn from them. Thank you!

*   [Christian Chiarulli](https://www.chrisatmachine.com/) ([@chrisatmachine](https://twitter.com/chrisatmachine)) - Author of [LunarVim](https://www.lunarvim.org)
*   [TJ DeVries](https://www.twitch.tv/teej_dv) ([@TeejDeVries](https://twitter.com/TeejDeVries)) - Neovim Core Member, [Streamer](https://www.twitch.tv/teej_dv)
*   [Jaime González García](https://www.barbarianmeetscoding.com/) ([@Vintharas](https://twitter.com/Vintharas)) - Goolge Engineer, Vim enthusiast, and [blogger](https://www.barbarianmeetscoding.com)
*   [Greg Hurrell](https://wincent.com/) ([@wincent](https://twitter.com/wincent)) - Great Vim video series on [YouTube](https://www.youtube.com/c/GregHurrell)
*   [Drew Neil](http://drewneil.com/) ([@nelstrom](https://twitter.com/nelstrom)) - Author of [Vimcasts](http://vimcasts.org/)
*   [ThePrimeagen](https://www.twitch.tv/ThePrimeagen) ([@theprimeagen](https://twitter.com/theprimeagen)) - Netflix engineer, [Streamer](https://www.twitch.tv/ThePrimeagen)
*   [Chris Toomey](https://ctoomey.com/) ([@christoomey](https://twitter.com/christoomey)) - Great Vim and Tmux learning resources

### [](#learn-from-the-terminal)Learn from the Terminal

And then there is `vimtutor`, I would be remiss if I didn't mention it. You can execute the interactive vim tutor from your terminal and there is a surprising amount of information that you can learn about using vim.

[](#setting-up-tmux-for-console-management)Setting up Tmux for Console Management
---------------------------------------------------------------------------------

I found that using `tmux` has been a great compliment to `neovim`. I typically have a `tmux` session per project I'm working on and I have multiple windows per project. I tend to have at least 4 windows per project; a window with `neovim` running, a window to run the server for that project, a window to interact with git, and a scratch window to run miscellaneous terminal commands.

### [](#installing-tmux)Installing Tmux

```
brew install tmux
```

> NOTE: My `tmux` prefix is mapped to the `<ctrl><space>` (more accurately `set -g prefix C-Space`)

### [](#helpful-vim-plugins)Common Tmux Commands

![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQ0MCIgaGVpZ2h0PSI4MDkiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4xIi8+)![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

The above picture shows switching between tmux sessions and windows with `<ctrl><space>w`. The following are some common commands that I use when coding.

*   `<ctrl><space>w` - list all tmux sessions and windows
*   `<ctrl><space>d` - detach from tmux to terminal prompt
*   `<ctrl><space>r` - reload tmux from configuration file
*   `tmux kill-session` - kill the current tmux session that you are in
*   `tmux kill-server` - kill the tmux server (kills all open sessions)
*   `tmux attach-session -t blog` - attach to an existing tmux session
*   `tmux ls` - list all tmux
*   `<ctrl><space>|` - create a new horizontal split
*   `<ctrl><space>-` - create a new vertical split
*   `<ctrl><space>?` - list help commands

> NOTE: You can take a look at my custom [`.tmux.conf`](https://github.com/elijahmanor/dotfiles/blob/master/tmux/.tmux.conf) from my dotfiles repo.

### [](#helpful-tmux-cheatsheets)Helpful Tmux Cheatsheets

The following are some tmux specific cheatsheets that I've found heplful as I navigate tmux and try out numerous features.

*   [Cheatsheet for tmux](https://github.com/neovim/nvim-lspconfig) by [devhints](https://devhints.io/)
*   [Tmux Cheat Sheet & Quick Reference](https://github.com/hrsh7th/nvim-cmp)
*   [Dash Tmux cheatsheet](https://github.com/glepnir/lspsaga.nvim) by [Kapeli](https://twitter.com/kapeli) maker of [Dash](https://kapeli.com/dash)

### [](#helpful-tmux-plugins)Helpful Tmux Plugins

Much like you can have plugins for `vim`, you can also have plugins for `tmux`. The plugin manager that I use is called [`tpm`](https://github.com/tmux-plugins/tpm).

The preferred way to install the `tpm` is by cloning the repo onto your machine into the hidden `.tmux` folder.

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

#### [](#file-management)Tmux Plugins

![](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjU4OSIgaGVpZ2h0PSIxMjkyIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEuMSIvPg==)![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

In addition to the dracula theme providing style and colors, it also provides several plugins to show `battery`, `cpu-usage`, `gpu-usage`, `ram-usage`, `network`, `network-bandwith`, `weather`, and `time`. I typically only set `cpu-usage ram-usage time` (as seen in other screenshots), but the above picture shows some of the other settings.

*   [tmux-sensible](https://github.com/nvim-telescope/telescope.nvim) - A sensible set of tmux options that you probably should set
*   [vim-tmux-navigator](https://github.com/nvim-telescope/telescope-fzf-native.nvim) - Will allow you to navigate seamlessly between vim and tmux splits using a consistent set of hotkeys.
*   [tmux-vi-navigation](https://github.com/kyazdani42/nvim-tree.lua) - Simplified shortcuts for tmux navigation
*   [tmux-fzf-url](https://github.com/wfxr/tmux-fzf-url) - A tmux plugin for opening urls from browser quickly without mouse.
*   [dracula](https://github.com/dracula/tmux) - A dark theme for tmux

#### [](#vim-plugin)Vim Plugin

*   [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator) - This `vim` plugin works in conjunction with the `vim-tmux-navigator` tmux plugin listed above.

### [](#additional-learning-resources)Additional Learning Resources

*   [Tmux](https://thoughtbot.com/upcase/tmux) taught by [Chris Toomey](https://ctoomey.com/) ([@christoomey](https://twitter.com/christoomey)) and provided by [@thoughtbot](https://twitter.com/thoughtbot)

### [](#helpful-bash-program)Helpful Bash Program

Instead of manually creating tmux sessions, renaming them, setting up custom windows, etc... I took the [`tat`](https://github.com/thoughtbot/dotfiles/blob/master/bin/tat) bash program developed by thoughtbot and [made my own tweaks](https://github.com/elijahmanor/dotfiles/blob/master/bin/bin/tat).

When `tat` in invoked it will create a tmux session and name it as the current folder's name. Then it will create a set of defined windows and layouts. I rarely ever manually create sessions or windows because of this program.

[](#kitty-or-alacritty)Kitty or Alacritty
-----------------------------------------

I starting using iTerm2, but found the redraw speed in the terminal wasn't quite what I wanted when using both Tmux and Neovim exclusively.

Thankfully there are 2 GPU-based terminal emulators you can use to help speed up rendering. I currently have both [Kitty](https://sw.kovidgoyal.net/kitty/) and [Alacritty](https://github.com/alacritty/alacritty) installed. Each has its pros and cons, but both are good alternatives for a snappier render. I typically stick with Kitty since it has ligature support.

```
brew install --cask kitty
brew install --cask alacritty
```

[](#get-a-buddy-to-join-you)Get a Buddy to Join You
---------------------------------------------------

There are many different development teams where I work. I lead a small team of 3 developers in my Front-End fire team. We decided to take on the adventure of using `neovim` and `tmux` together.

Being on this journey together has made the experience that much more fun. We regularly share things we are learning and when we are on pairing sessions the following questions or statements are common...

### [](#as-the-driver-of-a-pairing-session)As the driver of a pairing session

*   I found an awesome plugin/setting, let me show you!
*   Let's try to do that again, but more efficiently.

### [](#as-the-viewer-of-a-pairing-session)As the viewer of a pairing session

*   Whoa, what did you just do?
*   How did you just do that?
*   What setting/plugin was that?
*   Have you considered trying XYZ?

We will also take time to pause and try to figure out a better way to navigate or make a series of edits to push ourselves to become more efficient.

