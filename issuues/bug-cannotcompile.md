---
name: Bug report
about: compile error
title: 'error caused when 'yarn compile' run'
labels: 'yarn', 'typescript'
assignees: ''
---

## Bug Report

### Desktop (please complete the following information):**

- OS:  Windows 11 22H2
- Vim
  VIM - Vi IMproved 9.0 (2022 Jun 28, compiled May 13 2023 22:50:01)

### Describe the bug

ダウンロードコマンドに`curl`設定すると、JetpackSync実行時にエラーが発生する

**To Reproduce**

` vim: vimrc
" jetpack

# let g:jetpack_download_method = 'git'

let g:jetpack_download_method = 'curl'
" packadd vim-jetpack

" plugins
call jetpack#begin()
Jetpack 'tani/vim-jetpack', { 'opt': 1 }  " bootstrap

" my plugins
Jetpack 'editorconfig/editorconfig-vim'
Jetpack 'wakatime/vim-wakatime'
Jetpack 'lambdalisue/fern.vim'

call jetpack#end()



```



### Screenshots

``` terminal
function jetpack#sync[3]..jetpack#download_plugins[39]..jetpack#jobwait[3]..jetpack#jobcount[1]..<lambda>13098[1]..jetpack#jobstatus[4]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb の処理>中にエラーが検出されました:
行    5:
`cmd.exe /c (if exist C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim rmdir /s /q C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim) && mkdir C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim && curl -fsSL https://github.com/lambdalisue/fern.vim/archive/HEAD.tar.gz -o C:\Users\ATSUSH~1\AppData\Local\Temp\V8GC397.tmp && tar -zxf C:\Users\ATSUSH~1\AppData\Local\Temp\V8GC397.tmp -C C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim 1 && (if exist C:\Users\ATSUSH~1\AppData\Local\Temp\V8GC397.tmp del C:\Users\ATSUSH~1\AppData\Local\Temp\V8GC397.tmp)`:C:\app\scoop\apps\unxutils\current\usr\local\wbin\tar.exe: Cannot use compressed or remote archives^M^@C:\app\scoop\apps\unxutils\current\usr\local\wbin\tar.exe: Error is not recoverable: exiting now

```
