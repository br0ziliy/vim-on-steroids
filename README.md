Vim on steroids
---------------

My Vim config, based on
[https://github.com/Netherdrake/Dotfiles/blob/master/common/.vimrc](Nethrdrake's
.vimrc)

Installation
============

```bash
git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
curl ... > ~/.vim/vimrc
ln -s ~/.vim/vimrc ~/.vimrc
for dir in swap backup undo;do mkdir -p ~/vim/tmp/${dir};done
sudo dnf -y install ack ctags the_silver_searcher
vim +PluginInstall +qall
pushd ~/.vim/bundle/YouCompleteMe
./install.sh --clang-completer
popd
```

Usage
=====

|Function|Hotkey|
-----------------
|Switch to next tab|gt|
|Switch to previous tab|gT|
