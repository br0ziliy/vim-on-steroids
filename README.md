Vim on steroids
===============

My Vim config, based on
[Netherdrake's .vimrc](https://github.com/Netherdrake/Dotfiles/blob/master/common/.vimrc)
You might want to check Johns' [VimTricks videos](https://www.youtube.com/user/MinuteVimTricks) on YouTube

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

If you did not use [powerline]() before, you'll need to also install patched
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

|Function|Hotkey|
|--------|------|
|Switch to next tab|gt|
|Switch to previous tab|gT|
|Toggle [Gundo](http://bitbucket.org/sjl/gundo.vim) window|`<leader>1`|
|Toggle [Paste mode](http://vim.wikia.com/wiki/Toggle_auto-indenting_for_code_paste)|`<leader>2`|
|Toggle [TagList](http://vim-taglist.sourceforge.net/) window|`<leader>3`|
|Toggle [Tagbar](http://majutsushi.github.com/tagbar/) window|`<leader>4`|
|Toggle [NERDtree](http://github.com/scrooloose/nerdtree) window|`<leader>5`|
