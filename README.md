# vim-taglist
fixed taglist focked from vim-script, works well with NERDTree and other plugins

This is a fork from https://github.com/vim-scripts/taglist.vim

By default this old taglist plugin would only set the window size of it's self when toggle on/off or zoom in/out.
And here we have some small problems:
1. When there are several windows open at the same time, this might change sizes of other windows.
2. If you maxisized the taglist window with 'x' and then you toggled it off directly without restoring the window, it won't maxisize the taglist window properly at the very first time you press 'x' after you toggle it on again.

So I made some changes to fix these without changing other features.

It needs you to install ctags on your computer.
To install it with Vundle, first in your .vimrc or _vimrc add:
  Plugin 'chudyu/vim-taglist'
  and then use command :PluginInstall in vim.
  
Example of .vimrc configuration:
  " ----- ctags, taglist ----- {{{
  " --- ctags ---
  " dont miss ';'
  set tags=tags;
  set autochdir
  
  " --- taglist ---
  Plugin 'vim-scripts/taglist.vim'
  " let Tlist_WinWidth = 30
  let Tlist_Use_Right_Window = 1
  let Tlist_Max_Tag_Length = 10
  " only display tags defined only in the current buffer
  " let Tlist_Show_One_File = 1
  " let Tlist_Auto_Highlight_Tag = 0
  "  let Tlist_Auto_Open = 1
  " let Tlist_Auto_Update = 0
  " let Tlist_Close_On_Select = 1
  " 是否使用空行分隔不同类型tags
  let Tlist_Compact_Format = 0
  " 是否显示函数原型
  let Tlist_Display_Prototype = 1
  " automatically move to taglist window
  let Tlist_GainFocus_On_ToggleOpen = 1
  " 是否自动折叠不活动文件的tags,使用nerdtree时别打开
  " let Tlist_File_Fold_Auto_Close = 1
  " 作为最后一个窗口时是否自动关闭
  let Tlist_Exit_OnlyWindow = 1
  " 是否自动跳到当前buffer对应的tags
  " let Tlist_Highlight_Tag_On_BufEnter = 0
  " 在Tags菜单显示当前buffer的tags
  " let Tlist_Show_Menu = 1
  " 是否后台处理，默认0
  " let Tlist_Process_File_Always = 1
  let Tlist_Enable_Fold_Column = 0
  " 一些命令,比如按d删除后重新加入
  " :TlistAddFiles
  " :TlistAddFilesRecursive myproject *.java
  " F8开关Taglist
  noremap <F8> :TlistToggle<CR>
  "  }}}


For more information of the usages of the plugin, you can visit the taglist plugin homepage:
http://vim-taglist.sourceforge.net
