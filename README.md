Vim on steroids
---------------

My Vim config, based on (https://github.com/Netherdrake/Dotfiles/blob/master/common/.vimrc)[Nethrdrake's .vimrc]

Installation
============

git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
curl ... > ~/.vim/vimrc
ln -s ~/.vim/vimrc ~/.vimrc
for dir in swap backup undo;do mkdir -p ~/vim/tmp/${dir};done
sudo dnf install ack ctags
vim +PluginInstall +qall
cd ~/.vim/bundle/YouCompleteMe
./install.sh --clang-completer
