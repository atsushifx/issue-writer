# Bug Report

## Desktop (please complete the following information):**

- OS:  Windows 11 22H2
- Vim
  VIM - Vi IMproved 9.0 (2022 Jun 28, compiled May 13 2023 22:50:01)

## Describe the bug

When the download command is set to `curl`, an error occurs when executing JetpackSync.

## To Reproduce

Write the vimrc as follows:

``` vim: vimrc
" jetpack
let g:jetpack_download_method = 'curl'

 packadd vim-jetpack

" plugins
call jetpack#begin()
Jetpack 'tani/vim-jetpack', { 'opt': 1 }  " bootstrap

" my plugins
Jetpack 'editorconfig/editorconfig-vim'
Jetpack 'wakatime/vim-wakatime'
Jetpack 'lambdalisue/fern.vim'

call jetpack#end()
```

Start vim and execute JetpackSync.

## Screenshots

``` terminal
An error was detected while processing function jetpack#sync[3]..jetpack#download_plugins[39]..jetpack#jobwait[3]..jetpack#jobcount[1]..<lambda>13098[1]..jetpack#jobstatus[4]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb[2]..jetpack#nvim_exit_cb:
Line 5:
`cmd.exe /c (if exist C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim rmdir /s /q C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim) &&
  mkdir C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim &&
  curl -fsSL https://github.com/lambdalisue/fern.vim/archive/HEAD.tar.gz -o C:\Users\ATSUSH~1\AppData\Local\Temp\VCO5676.tmp &&
  tar -zxf C:\Users\ATSUSH~1\AppData\Local\Temp\VCO5676.tmp -C C:\Users\atsushifx\.config\vimfiles\pack\jetpack\opt\fern.vim 1 &&
  (if exist C:\Users\ATSUSH~1\AppData\Local\Temp\VCO5676.tmp del C:\Users\ATSUSH~1\AppData\Local\Temp\VCO5676.tmp)`

 C:\app\scoop\apps\unxutils\current\usr\local\wbin\tar.exe: Cannot use compressed or remote archives
 C:\app\scoop\apps\unxutils\current\usr\local\wbin\tar.exe: Error is not recoverable: exiting now

```
