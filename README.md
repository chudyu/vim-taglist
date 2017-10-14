# vim-taglist
Fixed taglist works well with NERDTree and other plugins.

This is a fork from [vim-scripts/taglist.vim](https://github.com/vim-scripts/taglist.vim)

## Problems fixed
By default the old taglist plugin would only set the window size of it's self when toggle on/off or zoom in/out. This may cause these problems:
* When there are several windows open at the same time, this might change sizes of other windows.
* If you maxisized the taglist window with 'x' and then you toggled it off directly without restoring the window, the next time you open it, you won't be able to maxisize it with the first 'x'.

So I made some changes to fix these without changing other features.

## Requirements
ctags should be installed on your computer.<br>
On Debian:<br>
```
apt-get install ctags
```
On Windows:<br>
>1. Download 'ctags58.zip' form http://ctags.sourceforge.net/ and unzip it to where you like.
>2. Set environment variables for ctags.exe

## Install
You can install it via Vundle:
```vim
  Plugin 'chudyu/vim-taglist'
```
Then use `:so %` and `:PluginInstall` in vim to install it.

## Configuration
The same with original taglist.
Example:
```vim
  " ----- ctags, Taglist {{{
  " --- ctags ---
  set tags=tags;
  set autochdir

  " --- taglist ---
  Plugin 'vim-scripts/taglist.vim'
  " let Tlist_WinWidth = 30
  let Tlist_Use_Right_Window = 1
  " let Tlist_Auto_Open = 1
  " let Tlist_Auto_Update = 0
  " let Tlist_Close_On_Select = 1
  let Tlist_Display_Prototype = 1
  let Tlist_GainFocus_On_ToggleOpen = 1
  let Tlist_Exit_OnlyWindow = 1
  " process at background:
  " let Tlist_Process_File_Always = 1
  let Tlist_Enable_Fold_Column = 0
  " Keymap: <F8>
  noremap <F8> :TlistToggle<CR>
  "  }}}
```
Commands to add files manually:<br>
Single file `:TlistAddFiles yourfile`<br>
Or recursively `:TlistAddFilesRecursive yourproject *.java`

For more information of the configuration and usages, you can visit the homepage of original taglist project:<br>
http://vim-taglist.sourceforge.net
