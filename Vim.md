***借鉴自 vim-vide 的文档***

# 目录

  - [vim的五种模式](#vim%E7%9A%84%E4%BA%94%E7%A7%8D%E6%A8%A1%E5%BC%8F)
  - [vim的哲学](#vim%E7%9A%84%E5%93%B2%E5%AD%A6)
- [vim基本操作](#vim%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C)
  - [打开/切换文件](#%E6%89%93%E5%BC%80%E5%88%87%E6%8D%A2%E6%96%87%E4%BB%B6)
  - [退出/保存](#%E9%80%80%E5%87%BA%E4%BF%9D%E5%AD%98)
  - [编辑](#%E7%BC%96%E8%BE%91)
  - [删除](#%E5%88%A0%E9%99%A4)
  - [移动](#%E7%A7%BB%E5%8A%A8)
  - [复制/粘贴](#%E5%A4%8D%E5%88%B6%E7%B2%98%E8%B4%B4)
  - [搜索](#%E6%90%9C%E7%B4%A2)
- [vim进阶](#vim%E8%BF%9B%E9%98%B6)
  - [代码补全](#%E4%BB%A3%E7%A0%81%E8%A1%A5%E5%85%A8)
  - [拖动功能](#%E6%8B%96%E5%8A%A8%E5%8A%9F%E8%83%BD)
  - [设置编码和格式](#%E8%AE%BE%E7%BD%AE%E7%BC%96%E7%A0%81%E5%92%8C%E6%A0%BC%E5%BC%8F)
  - [代码折叠](#%E4%BB%A3%E7%A0%81%E6%8A%98%E5%8F%A0)
  - [分割窗口](#%E5%88%86%E5%89%B2%E7%AA%97%E5%8F%A3)
  - [宏](#%E5%AE%8F)
- [vim插件](#vim%E6%8F%92%E4%BB%B6)
  - [必装插件](#%E5%BF%85%E8%A3%85%E6%8F%92%E4%BB%B6)
  - [NERDTree操作命令](#nerdtree%E6%93%8D%E4%BD%9C%E5%91%BD%E4%BB%A4)
  - [TagList操作命令(需要用到Ctags)](#taglist%E6%93%8D%E4%BD%9C%E5%91%BD%E4%BB%A4%E9%9C%80%E8%A6%81%E7%94%A8%E5%88%B0ctags)
  - [vim-commentary操作命令](#vim-commentary%E6%93%8D%E4%BD%9C%E5%91%BD%E4%BB%A4)
- [部分插件配置文档（一般在~/.vim/vimrc下）](#%E9%83%A8%E5%88%86%E6%8F%92%E4%BB%B6%E9%85%8D%E7%BD%AE%E6%96%87%E6%A1%A3%E4%B8%80%E8%88%AC%E5%9C%A8vimvimrc%E4%B8%8B)
  - [配置文件操作](#%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E6%93%8D%E4%BD%9C)
  - [TagList](#taglist)
    - [需要用到 Ctags（带$的表示为Linux系统Shell提示符）](#%E9%9C%80%E8%A6%81%E7%94%A8%E5%88%B0-ctags%E5%B8%A6%E7%9A%84%E8%A1%A8%E7%A4%BA%E4%B8%BAlinux%E7%B3%BB%E7%BB%9Fshell%E6%8F%90%E7%A4%BA%E7%AC%A6)
    - [修改配置（~/.vim/vimrc 下可修改）](#%E4%BF%AE%E6%94%B9%E9%85%8D%E7%BD%AEvimvimrc-%E4%B8%8B%E5%8F%AF%E4%BF%AE%E6%94%B9)
- [资源](#%E8%B5%84%E6%BA%90)
  - [vim资源](#vim%E8%B5%84%E6%BA%90)
  - [其他](#%E5%85%B6%E4%BB%96)

# Command

### vim的五种模式

```
1. 插入模式（和普通编辑器的模式差不多）
2. 普通模式
3. 可视模式
4. 命令行模式（扩展vim的功能，vim的精髓所在）
5. 选择模式（不常用）
```

### vim的哲学

```bash
执行次数 + 操作 + 范围
次数 1,2,3
操作 v d c
范围 a i w p $ " ' { ( [ t

 ni hao tang jun xin
 $('nihao')
 <a href="xx" >kjkjk </a> 
```

## vim基本操作

### 打开/切换文件

* 打开文件   
`:e file_name` 、`:o file_name`

* 如果使用`vim file1 file2 [filen]`命令打开多个文件，就可以使用`:args file_name`命令在打开的文件之间切换     
`:args file_name`

* 查看缓冲区中的文件列表    
`:buffers`、`:ls`、`files` 

* 切换到下一个缓冲区文件     
`:bnext`

* 切换到上一个缓冲区文件    
`:bprevious`、`bpre` 

* 切换到第一个缓冲区文件     
`:bfirst` 

* 切换到最后一个缓冲区文件     
`:blast`

* 删除缓冲区文件        
`:bdelete file_name`      

* 添加文件到缓冲区    
`:badd file_name`


### 退出/保存

* 保存    
`:w` 

* 强制保存，不退出vim    
`:w!`

* 退出    
`:q` 

* 强制退出不保存    
`:q!`

* 保存并退出     
`:wq`、`ZZ`

* 强制保存，并退出    
`:wq!` 

* 将修改另存到file中，不退出vim     
`:w file` 

* 放弃所有修改，从上次保存文件开始再编辑命令历史     
`:e!`    

### 编辑

* 编辑      
`i`/`I` 

* 退出编辑模式      
`esc`

* 撤销操作       
`u`       

* 重做（恢复被撤销的动作）      
`<Ctrl> + r ` 

* 清空当前行并进入编辑模式    
`cc` 、`C`、`S`

* 删除当前字符并进入编辑模式    
`s`   

* 替换当前字符（替换后不进入编辑模式）    
`r` 

* 持续替换字符（不进入编辑模式），替换一个光标自动移到下一个     
`R`      

* 格式化当前行代码           
`=-`  

* 格式化所有代码       
`gg=G`

* 可视化多选       
`<Shift> + v`

* 设置鼠标可区域选择，跟普通的编辑器一样可以进行拖选     
`:set mouse=a`

### 删除

* 删除当前行     
`dd`

* 删除包含当前行的n行数据（从当前行往下删除）    
`ndd`

* 删除包含当前行及之后的全部行    
`dG`

### 移动

* 跳转到首行    
`gg`  

* 跳转到尾行    
`G`

* 跳转到第n行    
`:n`、`nG`

* 在下一行插入     
`o`   

* 在上一行插入   
`O`   

* 移动到下一个单词开头    
`w`、`W`  

* 移动到上一个单词开头    
`b`、`B` 

* 移动到下一个单词结尾    
`e`、`E` 

* 下一段落     
`{`   

* 上一段落     
`}`  

* 跳转到文件内容的中部    
`M`   

* 跳转到文件内容的顶部    
`H`   

* 跳转到文件内容的底部    
`L`  

### 复制/粘贴

* 复制    
`y`      

* 粘贴到下部   
`p`   

* 粘贴到上部    
`P`  

* 剪切      
`x`、`X`

### 搜索

* 当前行搜索，til，正向 / 反向    
`f`  / `F`    

* 当前行搜索，until，正向 / 反向    
`t` / `T`   

* 重复当前行搜索      
`;`、`,`  

* 当前文件搜索，向上搜索 / 向下搜索    
`/`、`?`    

* 跨文件搜索     
`:grep -r` / `:!grep -r`

* 下一个匹配内容     
`n`   

* 上一个匹配内容    
`N`    

* 清除搜索高亮    
`ctrl-L`    

## vim进阶

### 代码补全

* 往前搜索补全     
`<Ctrl> + p `

* 往后搜索补全     
`<Ctrl> + n ` 

* 取消补全     
`<Ctrl> + e `

* 确定补全     
`<Ctrl> + y `

### 拖动功能

* 将当前行定位到屏幕中间     
`zz`

* 将当前行定位到屏幕底部     
`zb` 

* 将当前行定位到屏幕顶部     
`zt`

### 设置编码和格式

* 让换行符自由切换       
`:set fileformat unix dos mas`     

* 检测打开文档编码的顺序，一般设置为utf-8、cp936     
`:set fileencodings`   

* 保存文档的编码，一般为utf-8    
`:set fileencoding`    

* vim本身界面的编码，一般和文档无关     
`:set encoding`   

* `NERDTree-Find`
`\3` 

* `:set filetype=awk`     
`\a`

* `:set filetype=css`    
`\c`

* `:set filetype=html`    
`\h`

* `:set filetype=javascript`    
`\j`   

* `:set filetype=lua`    
`\l` 

* `:set filetype=markdown`   
`\m`  

* `:set filetype=php`   
`\p`

* `:set filetype=sh`     
`\s`

* `:set filetype=vim`     
`\v` 

* `:set filetype=python`     
`\y`

### 代码折叠

* 创建折叠     
`zf`   

* 打开折叠      
`zo`

* 关闭折叠     
`zc` 

* 保存，载入绘画    
`:mkview` / `:loadview`

### 分割窗口

* 水平分割    
`:split [file_name]` 、`:sp [file_name]`    

* 垂直分割       
`:vsplit [file_name]`、`:vs [file_name]`    

* 将焦点移动到左边窗口     
`<Ctrl> + w + h`    

* 将焦点移动到下方窗口     
`<Ctrl> + w + j`  

* 将焦点移动到上方窗口     
`<Ctrl> + w + k`    

* 将焦点移动到右边窗口     
`<Ctrl> + w + l`  

### 宏

* 录制到a     
`qa`

* 播放a     
`@a`

## vim插件

### 必装插件

* php文档，`<s-k>`查询     
`vim-phpmanual`

* 语法检查    
`syntastic`   

* 文件跳转    
`ctrlp.vim`   

* 浏览文件   
`nerdtree` 

* 观察git状态    
`vim-gitgutter`   

* 强大的注释插件    
`vim-commentary`

### NERDTree操作命令

* 打开 NERDTree操作命令   
`NERDTree`

* 打开/关闭文件或目录       
`o`  

* 在新标签页中打开     
`t`

* 在后台标签页打开    
`T`

* 执行此文件    
`!`

* 到上层目录    
`p`

* 到根目录    
`P`

* 到第一个节点    
`K`

* 到最后一个节点    
`J` 

* 打开上层目录     
`u`

* 显示文件系统菜单（添加、删除、移动操作）   
`m`

* 帮助，再按一下关闭   
`?`

* 关闭       
`q`

* `NERDTree-Find`   
`\3` 

### TagList操作命令(需要用到Ctags)

*  打开 Tlist      
`TlistOpen`

* 关闭 Tlist       
`TlistClose`

* 切换标签列表窗口状态(打开←→关闭)    
`TlistToggle`

* 跳到光标所在函数或者结构体的定义处     
`Ctrl+ ]`

* 返回查找或跳转    
`Ctrl+ T`

* 遇到 * of * or more注释定义的情况，查找多个定义   
`g + ]`

### vim-commentary操作命令

* 注释当前行（普通模式下）  
`gcc`

* 注释当前选中内容（可视多选模式下） 
`gc`   

* 注释当前所在段落     
`gcap`

* 注释上一次注释的部分     
`gcu`

* 取消一组相邻的注释    
`gcgc`

## 部分插件配置文档（一般在~/.vim/vimrc下）

### 配置文件操作

* 退出并保存后，然后执行.vimrc    
`source ~/.vimrc`

### TagList

#### 需要用到 Ctags（带$的表示为Linux系统Shell提示符）

* 在当前文件夹下生成ctags文件    
`$ctags –R`

* 跳转到所要查找的变量/函数名（tag为您欲查找的变量/函数名）   
`$vi –t tag`

#### 修改配置（~/.vim/vimrc 下可修改）

* 加载tags文件路径    
`set tags=./tags,tags;$HOME`   

* 设置ctags路径    
`let Tlist_Ctags_Cmd = '/usr/bin/ctags'`   

* 启动vim后自动打开taglist窗口     
`let Tlist_Auto_Open = 1`

* 不同时显示多个文件的tag，仅显示一个   
`let Tlist_Show_One_File = 1`   

* taglist为最后一个窗口时，退出vim    
`let Tlist_Exit_OnlyWindow = 1` 

* taglist窗口显示在右侧，缺省为左侧    
`let Tlist_Use_Right_Window =1` 

* 设置taglist窗口大小    
`let Tlist_WinHeight = 100` 

*  同上*   
`let Tlist_WinWidth = 40` 


## 资源

### vim资源

- [Vimbits](http://www.vimbits.com/)
- [简明 Vim 练级攻略 | 酷 壳 - CoolShell.cn](http://coolshell.cn/articles/5426.html)
- [[翻译]130+vim基本命令](http://wklken.me/posts/2013/08/17/130-essential-vim-commands.html#stq=&stp=0)
- [Vimer的程序世界 | 一个vim使用者的程序世界](http://www.vimer.cn/)
- [Vim实用技巧 (豆瓣)](https://book.douban.com/subject/25869486/)
- [welcome home : vim online](http://www.vim.org/)
- [Vim | 易水博客](http://easwy.com/blog/archives/tag/vim/)
- [Vimcasts - Free screencasts about the text editor Vim](http://vimcasts.org/)
- [VimGolf - real Vim ninjas count every keystroke!](http://vimgolf.com/)
- [Vim Awesome](http://vimawesome.com/)
- [像IDE一样使用Vim](https://github.com/yangyangwithgnu/use_vim_as_ide#4.7)

### 其他

- [用DBGPavim在Vim中调试PHP/Python程序](https://brookhong.github.io/2014/09/27/dbgpavim-cn.html)
- [Cscope的使用（领略Vim + Cscope的强大魅力） - 面码的个人空间 - 开源中国社区](http://my.oschina.net/u/572632/blog/267471)
- [VundleVim/Vundle.vim](https://github.com/VundleVim/Vundle.vim)
- [Using tab pages - Vim Tips Wiki - Wikia](http://vim.wikia.com/wiki/Using_tab_pages)
- powerline / airline