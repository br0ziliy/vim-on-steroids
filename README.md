Vim on steroids
===============

My Vim config, based on
[Netherdrake's .vimrc](https://github.com/Netherdrake/Dotfiles/blob/master/common/.vimrc)

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
