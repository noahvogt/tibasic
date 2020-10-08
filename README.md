# Noah's TI Basic Program Collection

## Why do I use .tibasic files?

This repository only contains .tibasic **Source Code Files** instead of your typical compiled .8xp files from your TI Calculator. I have made this decision to have the *freedom* to edit my ti basic programs in any text editor. In my eyes, using the proprietary, official [TI Connect CE](https://education.ti.com/en/products/computer-software/ti-connect-ce-sw) editor is just a big pain. And don't even talk about programming directly on your TI-84.

In short, using Source Code Files makes *editing* and *sharing* easier and better.

## Compiling

I have made my own compiler called [tibasicc](https://github.com/noahvogt/tibasicc) so I can have the ability to use comments in my .tibasic files. It is very easy to install, just follow the instructions in the Readme. You can run the compiler on the command line like this:

    tibasicc [options] filename

## GNU/Linux Mentions

To fully programm and connect your TI Calculator *only* using GNU/Linux, you can use a programm called **TILP** *('Tilp Is a Linking Program')* to transfer your compiled .8xp files to your TI Calculator. On Arch Linux, there is an [AUR Package](https://aur.archlinux.org/packages/tilp/) available (simply called `tilp`).

For further informations and a list of features consider visiting their [Project Website](http://lpg.ticalc.org/prj_tilp/).

## Vim Mentions

To get some nice and easy *syntax highlighting* you can use the command `set syntax=python`. You can even set this behaviour as a default for all .tibasic files in your .vimrc:

    " automatic python syntax highlighting for .tibasic files
    autocmd BufNewFile,BufRead *.tibasic set filetype=python
