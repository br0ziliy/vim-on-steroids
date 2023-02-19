Vim on steroids
===============

My Vim config, based on
[Netherdrake's
.vimrc](https://github.com/Netherdrake/Dotfiles/blob/master/common/.vimrc).
You might want to check Johns' [VimTricks
videos](https://www.youtube.com/user/MinuteVimTricks) on YouTube as well.

The idea behind putting this to GitHub is that there're tons of cool configs
here and there. They all do have one tiny issue though - no, or little
documentation. Whoever wants to use those have to take his time to read through
all the plugins docs to find out what that config actually does. My goal is to
document mine in as much details as possible, so it becomes clear about what a
potential user can expect if he or she decides to use it.

Installation
------------

```bash
git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
curl https://raw.githubusercontent.com/br0ziliy/vim-on-steroids/master/vimrc > ~/.vim/vimrc
ln -s ~/.vim/vimrc ~/.vimrc
for dir in swap backup undo;do mkdir -p ~/vim/tmp/${dir};done
sudo dnf -y install ack ctags the_silver_searcher
vim +PluginInstall +qall
pushd ~/.vim/bundle/YouCompleteMe
./install.sh --clang-completer
popd
```

### Note on fonts

If you did not use
[powerline](https://powerline.readthedocs.org/en/master/overview.html) before, you'll need to also install patched
[powerline fonts](https://github.com/bling/vim-airline#integrating-with-powerline-fonts)
for proper airline display:

```
mkdir -p ~/.config/fontconfig/conf.d/
mkdir -p ~/.fonts
wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf
wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf
mv PowerlineSymbols.otf ~/.fonts/
mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/
fc-cache -vf ~/.fonts/
```

If airline still looks weird - try checking the [official
powerline-fonts](https://powerline.readthedocs.org/en/master/installation/linux.html#fonts-installation)
installation instructions.

Usage
-----

`leader` key is configured as `,` in this config.
When you see something like `<leader>0` in the table below - it means you have
to press `,`, then `0` on your keyboard. You can change this in vimrc, changing
`let mapleader=","` to your preference.

### General

|Function|Hotkey|
|--------|------|
|Open .vimrc|`<leader>v`|
|Toggle [Gundo](http://bitbucket.org/sjl/gundo.vim) window|`<leader>1`|
|Toggle [Paste mode](http://vim.wikia.com/wiki/Toggle_auto-indenting_for_code_paste)|`<leader>2`|
|Toggle [TagList](http://vim-taglist.sourceforge.net/) window|`<leader>3`|
|Toggle [Tagbar](http://majutsushi.github.com/tagbar/) window|`<leader>4`|
|Toggle [NERDtree](http://github.com/scrooloose/nerdtree) window|`<leader>5`|

### Tabs/Buffers/Windows and such

First, read this wonderful blogpost:
https://joshldavis.com/2014/04/05/vim-tab-madness-buffers-vs-tabs/
No, really - go and read it now, it's short and pretty useful.
Now when you're done - we can go on.
I'm using [CtrlP](https://github.com/kien/ctrlp.vim) for buffers navigation.
You just hit `<leader>bb` - and list of all buffers appears at the bottom of the
screen. You can start typing a buffer name, and the list will be narrowed to
what you type. Pressing `<leader>bm` opens a list of Most Recently Used files.
Again, typing a filename will narrow down the list. Very convenient.

<<<<<<< HEAD
### Misc. plugins usage

#### TaskWarrior

I'm using [TaskWarrior](http://taskwarrior.org/) to track my tasks and time
spend on each task. There're tons of frontends for TaskWarrior, but since Vim -
is the thing I see the most in front of me during the day, I decided to use
[vim-taskwarrior](https://github.com/blindFS/vim-taskwarrior) plugin.
Execute `:TW` to see your task list. I use the official [vim-taskwarrior keybindings](https://github.com/blindFS/vim-taskwarrior#default-map)
to operate my task list. The only customization I had to do to my `.vimrc` is this:
```
let g:task_rc_override = 'rc.defaultwidth=0 rc.defaultheight=0'
```
so vim-taskwarrior uses the full display width to show task descriptions.
### Navigation in a file

My setup includes [EasyMotion](https://github.com/easymotion/vim-easymotion)
plugin, which allows you to optimize how you navigate the text.
Just press `<Leader>f`, and then enter a letter you're looking for - all
matching letters on the current visible text will be highlighted. `<Leader>F`
does the same, only it searches "backwards" relative to current cursor position.
It's very powerful plugin, go and read [official
documentation](https://github.com/easymotion/vim-easymotion#usage-example-for-the-base-features),
it has very good examples of what you can do.
