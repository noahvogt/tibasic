# Noah's TI Basic Program Collection

## Why do I use .tibasic files?

This repository only contains .tibasic **Source Code Files** instead of your typical compiled .8xp files from your TI Calculator. I have made this decision to have the *freedom* to edit my ti basic programs in any text editor. In my eyes, using the proprietary, official [TI Connect CE](https://education.ti.com/en/products/computer-software/ti-connect-ce-sw) editor is just a big pain. And don't even talk about programming directly on your TI-84.

In short, using Source Code Files makes *editing* and *sharing* easier and better.

## Compiling

There is an unmaintained FOSS *(Free and Open Source Software)* [Project on Sourceforge](https://sourceforge.net/projects/tibasic/) to compile .tibasic Source Code Files to executable .8xp files. There is only an officially released package for Windows and unfortunately I haven't found (or even made) a GNU/Linux-Port yet. But as far as I have been testing, it worked perfectly in wine:

    wine [path to your .exe]/tibasic.exe [filename]

Note that my .tibasic files contain *comments* and *empty lines* that have to be removed before compiling, because the compiler lacks a preprocessor. You can archive for example using `sed`:

    sed "s/\s*#.*//g; /^$/ d" [inputfile] > [outputfile]

I have made a bash script that automates this process in the 'build-etc' directory *(Please note that you have to **manually** change the filepath of the .exe file in the script)* I recommend putting this file in your $PATH so you can *preprocess and compile* using this simple syntax:

    tibasicc [filename]

## GNU/Linux Mentions

To fully programm and connect your TI Calculator *only* using GNU/Linux, you can use a programm called **TILP** *('Tilp Is a Linking Program')* to transfer your compiled .8xp files to your TI Calculator. On Arch Linux, there is an [AUR Package](https://aur.archlinux.org/packages/tilp/) available (simply called `tilp`).

For further informations and a list of features consider visiting their [Project Website](http://lpg.ticalc.org/prj_tilp/).

## Vim Mentions

To get some nice and easy *syntax highlighting* you can use the command `set syntax=python`. You can even set this behaviour as a default for all .tibasic files in your .vimrc:

    " automatic python syntax highlighting for .tibasic files
    autocmd BufNewFile,BufRead *.tibasic set filetype=python
