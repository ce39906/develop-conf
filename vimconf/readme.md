# install basic vim conf

	mkdir -p ~/.vim/colors
	mkdir -p ~/.vim/plugin
	cp .vimrc ~/
	cp solarized.vim ~/.vim/colors
	cp minibufexpl.vim ~/.vim/plugin
	
# install plugin

## install Vundle

* git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
* add this below to your .vimrc

	```Txt
	set nocompatible              " be iMproved, required
	filetype off                  " required
	set rtp+=~/.vim/bundle/Vundle.vim
	call vundle#begin()
	Plugin 'VundleVim/Vundle.vim'
	call vundle#end()            " required
	filetype plugin indent on    " required
	```

* Launch vim and run :PluginInstall

## install YouCompleteMe with Vundle

* add this below in Vundle 

	```Txt
	Plugin 'Valloric/YouCompleteMe'
	```
* run :BundleInstall
	(this may take a few long time)
* conf YouCompleteMe

	```Txt
	cd ~/.vim/bundle/YouCompleteMe
	./install.py --clang-completer
	cp ~/.vim/bundle/YouCompleteMe/third_party/ycmd/examples/.ycm_extra_conf.py ~/
	```
* add this below after Plugin 'Valloric/YouCompleteMe' in your .vimrc

	```Txt
	let g:ycm_global_ycm_extra_conf='~/.ycm_extra_conf.py'
	let g:ycm_confirm_extra_conf=0
	```
* Launch vim and run :source ~/.vimrc
