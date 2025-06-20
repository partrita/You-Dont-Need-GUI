# You Don't Need GUI

[![Join the community on Spectrum](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/you-dont-need/GUI)

[中文版请看这里](./README-zh.md), [한국어 버전](./README-ko.md)

<details>
It's for noobs :)
</details>
<br />

Graphical user interfaces are super friendly to computer users. They were introduced in reaction to the perceived steep learning curve of command-line interfaces (CLIs).

![Xerox Star 8010 workstations](./data/Xerox_Stas_8010_workstations.jpg)

However, they often require more resources, are less powerful and hard to automate via scripting.

As a computer expert, we want to be more efficient and do our jobs better. We know that command words may not be easily discoverable or mnemonic, so we try to list some common tasks that you might be tempted to do in GUI.

## Quick links

1. [copy a file](#copy-a-file)
1. [duplicate a file](#duplicate-a-file)
1. [copy a directory](#copy-a-directory)
1. [duplicate a directory](#duplicate-a-directory)
1. [move a file](#move-a-file)
1. [rename a file](#rename-a-file)
1. [move a directory](#move-a-directory)
1. [rename a directory](#rename-a-directory)
1. [merge directories](#merge-directories)
1. [create a new file](#create-a-new-file)
1. [create a new directory](#create-a-new-directory)
1. [show file/directory size](#show-filedirectory-size)
1. [show file/directory info](#show-filedirectory-info)
1. [open a file with the default program](#open-a-file-with-the-default-program)
1. [open a file in any application](#open-a-file-in-any-application)
1. [zip a directory](#zip-a-directory)
1. [unzip a directory](#unzip-a-directory)
1. [peek files in a zip file](#peek-files-in-a-zip-file)
1. [remove a file](#remove-a-file)
1. [remove a directory](#remove-a-directory)
1. [remove all files of certain criteria](#remove-all-files-of-certain-criteria)
1. [list directory contents](#list-directory-contents)
1. [tree view a directory and its subdirectories](#tree-view-a-directory-and-its-subdirectories)
1. [find a stale file](#find-a-stale-file)
1. [show a calendar](#show-a-calendar)
1. [find a future date](#find-a-future-date)
1. [use a calculator](#use-a-calculator)
1. [force quit a program](#force-quit-a-program)
1. [check server response](#check-server-response)
1. [view content of a file](#view-content-of-a-file)
1. [search for a text in a file](#search-for-a-text-in-a-file)
1. [search in all files in current working directory, quickly (entire disk in less than 15 minutes)](#search-in-all-files-in-current-working-directory-quickly-entire-disk-in-less-than-15-minutes)
1. [view an image](#view-an-image)
1. [show disk size](#show-disk-size)
1. [check cpu usage, processes and RAM](#check-cpu-usage-processes-and-ram)
1. [know whether your computer is under load, and whether it's due to memory or CPU](#know-whether-your-computer-is-under-load-and-whether-its-due-to-memory-or-cpu)
1. [poweroff or reboot your computer](#poweroff-or-reboot-your-computer)
1. [locate USB drives](#locate-usb-drives)
1. [unmount USB drives](#unmount-usb-drives)
1. [format USB drives](#format-usb-drives)
1. [check USB format](#check-usb-format)
1. [run command on all files of a directory](#run-command-on-all-files-of-a-directory)
1. [check network connectivity to a remote address and port](#check-network-connectivity-to-a-remote-address-and-port)
1. [check DNS config of a domain](#check-dns-config-of-a-domain)
1. [check the ownership and registration of a domain](#check-the-ownership-and-registration-of-a-domain)
1. [Quick tips](#quick-tips)
1. [Hotkeys](#hotkeys)
1. [I can't remember these cryptic commands](#i-cant-remember-these-cryptic-commands)


## copy a file

**STOP DRAG AND DROPPING A FILE, OR CMD/CTRL + C, CMD/CTRL + V A FILE** :-1:

Copy `readme.txt` to the `documents` directory

```shell
$ cp readme.txt documents/
```
[Go to table of contents 🔼](#quick-links)


## duplicate a file

**STOP RIGHT CLICKING AND DUPLICATE A FILE** :-1:

```shell
$ cp readme.txt readme.bak.txt
```
More advanced:
```shell
$ cp readme{,.bak}.txt
# Note: learn how the {} works with touch foo{1,2,3}.txt and see what happens.
```
[Go to table of contents 🔼](#quick-links)


## copy a directory

**STOP DRAG AND DROPPING A DIRECTORY, OR CMD/CTRL + C, CMD/CTRL + V A DIRECTORY** :-1:

Copy `myMusic` directory to the `myMedia` directory

```shell
$ cp -a myMusic myMedia/
# or
$ cp -a myMusic/ myMedia/myMusic/
```
[Go to table of contents 🔼](#quick-links)


## duplicate a directory

**STOP RIGHT CLICKING AND DUPLICATE A DIRECTORY** :-1:

```shell
$ cp -a myMusic/ myMedia/
# or if `myMedia` folder doesn't exist
$ cp -a myMusic myMedia/
```
[Go to table of contents 🔼](#quick-links)


## move a file

**STOP DRAG AND DROPPING A FILE, OR CMD/CTRL + X, CMD/CTRL + V A FILE** :-1:

```shell
$ mv readme.txt documents/
```

**Always** use a trailing slash when moving files, [for this reason](http://unix.stackexchange.com/a/50533).

[Go to table of contents 🔼](#quick-links)

## rename a file

**STOP RIGHT CLICKING AND RENAME A FILE** :-1:

```shell
$ mv readme.txt README.md
```
[Go to table of contents 🔼](#quick-links)


## move a directory

**STOP DRAG AND DROPPING A DIRECTORY, OR CMD/CTRL + X, CMD/CTRL + V A DIRECTORY** :-1:

```shell
$ mv myMedia myMusic/
# or
$ mv myMedia/ myMusic/myMedia
```
[Go to table of contents 🔼](#quick-links)


## rename a directory

**STOP RIGHT CLICKING AND RENAME A DIRECTORY** :-1:

```shell
$ mv myMedia/ myMusic/
```
[Go to table of contents 🔼](#quick-links)


## merge directories

**STOP DRAG AND DROPPING TO MERGE DIRECTORIES** :-1:

```shell
$ rsync -a /images/ /images2/	# note: may over-write files with the same name, so be careful!
```
[Go to table of contents 🔼](#quick-links)


## create a new file

**STOP RIGHT CLICKING AND CREATE A NEW FILE** :-1:

```shell
$ touch 'new file'    # updates the file's access and modification timestamp if it already exists
# or
$ > 'new file'        # note: erases the content if it already exists
```
[Go to table of contents 🔼](#quick-links)


## create a new directory

**STOP RIGHT CLICKING AND CREATE A NEW DIRECTORY** :-1:

```shell
$ mkdir 'untitled folder'
# or
$ mkdir -p 'path/may/not/exist/untitled folder'
```
[Go to table of contents 🔼](#quick-links)


## show file/directory size

**STOP RIGHT CLICKING AND SHOW FILE/directory INFO** :-1:

```shell
$ du -sh node_modules/
```
[Go to table of contents 🔼](#quick-links)


## show file/directory info

**STOP RIGHT CLICKING AND SHOW FILE/DIRECTORY INFO** :-1:

```shell
$ stat -x readme.md   # on macOS
$ stat readme.md      # on Linux
```
[Go to table of contents 🔼](#quick-links)


## open a file with the default program

**STOP DOUBLE CLICKING ON A FILE** :-1:

```shell
$ xdg-open file   # on Linux
$ open file       # on MacOS
$ start file      # on Windows
```
[Go to table of contents 🔼](#quick-links)


## open a file in any application

**STOP RIGHT CLICKING AND OPEN WITH** :-1:

```shell
$ open -a appName file
```
[Go to table of contents 🔼](#quick-links)


## zip a directory

**STOP RIGHT CLICKING AND COMPRESS DIRECTORY** :-1:

```shell
$ zip -r archive_name.zip folder_to_compress
```
[Go to table of contents 🔼](#quick-links)


## unzip a directory

**STOP RIGHT CLICKING AND UNCOMPRESS DIRECTORY** :-1:

```shell
$ unzip archive_name.zip
```
[Go to table of contents 🔼](#quick-links)


## decompress files of any format

**STOP RIGHT CLICKING AND UNCOMPRESS DIRECTORY** :-1:

```shell
$ unar archive_name.zip
$ unar archive_name.7z
$ unar archive_name.rar
$ unar archive_name.ISO
$ unar archive_name.tar.gz
```
[Go to table of contents 🔼](#quick-links)


## peek files in a zip file

**STOP USING WinRAR** :-1:

```shell
$ zipinfo archive_name.zip
# or
$ unzip -l archive_name.zip
```
[Go to table of contents 🔼](#quick-links)


## peek files in a compress file of any format

**STOP USING WinRAR** :-1:

```shell
$ lsar -l archive_name.zip
$ lsar -l archive_name.7z
$ lsar -l archive_name.ISO
$ lsar -l archive_name.rar
$ lsar -l archive_name.tar.gz
```
[Go to table of contents 🔼](#quick-links)


## remove a file

**STOP RIGHT CLICKING AND DELETE A FILE PERMANENTLY** :-1:

```shell
$ rm my_useless_file
```

**IMPORTANT**: The `rm` command deletes `my_useless_file` permanently, which is equivalent to move `my_useless_file` to Recycle Bin and hit Empty Recycle Bin.

[Go to table of contents 🔼](#quick-links)

## remove a directory

**STOP RIGHT CLICKING AND DELETE A DIRECTORY PERMANENTLY** :-1:

```shell
$ rm -r my_useless_folder
```
[Go to table of contents 🔼](#quick-links)


## remove all files of certain criteria

```shell
$ find . -name "*.bak" -type f -delete
```

**IMPORTANT**: run `find . -name "*.bak" -type f` first to see exactly which files you will remove.

[Go to table of contents 🔼](#quick-links)

## list directory contents

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
$ ls my_folder        # Simple
$ ls -la my_folder    # -l: show in list format. -a: show all files, including hidden. -la combines those options.
$ ls -alrth my_folder # -r: reverse output. -t: sort by time (modified). -h: output human-readable sizes.
```
[Go to table of contents 🔼](#quick-links)


## tree view a directory and its subdirectories

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
$ tree                                                        # on Linux
$ find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'      # on MacOS
# Note: install homebrew (https://brew.sh) to be able to use (some) Linux utilities such as tree.
# brew install tree
```
[Go to table of contents 🔼](#quick-links)


## find a stale file

**STOP USING YOUR FILE EXPLORER TO FIND A FILE** :-1:

Find all files modified more than 5 days ago

```shell
$ find my_folder -mtime +5
```
[Go to table of contents 🔼](#quick-links)


## show a calendar

**STOP LOOKING UP WHAT THIS MONTH LOOKS LIKE BY CALENDAR WIDGETS** :-1:

Display a text calendar

```shell
$ cal
```
Display selected month and year calendar

```shell
$ cal 11 2018
```
[Go to table of contents 🔼](#quick-links)


## find a future date

**STOP USING WEBAPPS TO CALCULATE FUTURE DATES** :-1:

What is today's date?

```shell
$ date +%m/%d/%Y
```

What about a week from now?

```shell
$ date -d "+7 days"                                           # on Linux
$ date -j -v+7d                                               # on MacOS
```
[Go to table of contents 🔼](#quick-links)


## use a calculator

**STOP USING CALCULATOR WIDGET** :-1:

```shell
$ bc -l
```
[Go to table of contents 🔼](#quick-links)


## force quit a program

**STOP CTRL + ALT + DELETE and choose the program to kill** :-1:

```shell
$ killall -9 program_name
```
[Go to table of contents 🔼](#quick-links)


## check server response

**STOP OPENING A BROWSER** :-1:

```shell
$ curl -i umair.surge.sh
# curl's -i (--include) option includes HTTP response headers in its output.
```
[Go to table of contents 🔼](#quick-links)


## view content of a file

**STOP DOUBLE CLICKING A FILE** :-1:

```shell
$ cat apps/settings.py
# if the file is too big to fit on one page, you can use a 'pager' (less) which shows you one page at a time.
$ less apps/settings.py
```
[Go to table of contents 🔼](#quick-links)


## search for a text in a file

**STOP CMD/CTRL + F IN A FILE** :-1:

```shell
$ grep -i "Query" file.txt
```

![grep](./data/grep.jpg)

* grep lets you search files for text
    * `$ grep bananas foo.txt`
    * Here are some of my favourite grep command line arguments!

* `-E` aka `egrep`
    * Use if you want regexps like ".+" to work. otherwise you need to use "\.+"

* `-r` recursive!
    * Search all the files in a directory.

* `-v` invert match:
    * find all lines that don't match

* `-O` only print the matching part of the line (not the whole line)

* `-i` case insensitive

* `-l` only show the filenames of the files that matched

* `-a` search binaries:
    * treat binary data like it's text instead of ignoring it!

* `-A` Show context for your search.
    * `$ grep -A 3 foo`
    * will show 3 lines of context after a match

* `-F` don't treat the match string as a regex
    * eg `$ grep -F ...`

* grep alternatives
    * `ack`
    * `ag`
    * `ripgrep`
    * (better for searching code!)

[Go to table of contents 🔼](#quick-links)


## search in all files in current working directory, quickly (entire disk in less than 15 minutes)

**STOP CMD/CTRL + F IN A DIRECTORY** :-1:

```shell
$ ripgrep -i "Query"
# brew install ripgrep
```
[Go to table of contents 🔼](#quick-links)


## view an image

**STOP USING PREVIEW** :-1:

```shell
$ imgcat image.png
# Note: requires iTerm2 terminal.
```
[Go to table of contents 🔼](#quick-links)


## show disk size

**STOP RIGHT CLICKING DISK ICON OR OPENING DISK UTILITY** :-1:

```shell
$ df -h
```
[Go to table of contents 🔼](#quick-links)


## check cpu usage, processes and RAM

**STOP OPENING YOUR ACTIVITY MONITOR OR TASK MANAGER** :-1:

```shell
$ top
```
if you want some more details:
```shell
$ htop
```

[Go to table of contents 🔼](#quick-links)


## know whether your computer is under load, and whether it's due to memory or CPU

```shell
$ glances
# brew install glances
```
[Go to table of contents 🔼](#quick-links)


## poweroff or reboot your computer

This can be useful when you're patching a server that is accessed via SSH and you don't have a GUI.

```shell
# poweroff
$ sudo shutdown -h now
# reboot
$ sudo shutdown -r now
```
[Go to table of contents 🔼](#quick-links)


## locate USB drives

```shell
$ df
```
[Go to table of contents 🔼](#quick-links)


## unmount USB drives

```shell
$ sudo umount /dev/sdb1
```
[Go to table of contents 🔼](#quick-links)


## format USB drives

```shell
# FAT32
$ sudo mkfs.vfat /dev/sdb1
# NTFS
$ sudo mkfs.ntfs /dev/sdb1
# exFAT
$ sudo mkfs.exfat /dev/sdb1
```
[Go to table of contents 🔼](#quick-links)


## check USB format

```shell
$ sudo fsck /dev/sdb1
```
[Go to table of contents 🔼](#quick-links)


## run command on all files of a directory

**STOP CLICKING THE FILES ONE BY ONE** :-1:

```shell
$ for FILE in *; do echo $FILE; done
```
[Go to table of contents 🔼](#quick-links)

## check network connectivity to a remote address and port

**STOP USING NETWORK UTILITY**

```shell
$ nc -vz www.google.com 443
$ nc -vz 1.1.1.1 53
```

[Go to table of contents 🔼](#quick-links)

## check DNS config of a domain

**STOP USING NETWORK UTILITY**

```shell
$ dig www.google.com
```

[Go to table of contents 🔼](#quick-links)

## check the ownership and registration of a domain

**STOP USING NETWORK UTILITY AND THE WEBSITE OF DOMAIN REGISTRATION PROVIDERS**

```shell
$ whois www.google.com
```

[Go to table of contents 🔼](#quick-links)

## Quick tips

```bash
$ !! # run the last command executed
$ sudo !! # run the last command as root
$ !<word> # run last command starting with a specific word
$ !<word>:p # ^ list, but don't run that last command
$ <space>command # execute a command w/out saving in history
$ echo "ls -l" | at midnight # execute command at given time
$ caffeinate -u -t 3600 # stop your mac from sleeping for 1h
$ ls -lhS # sort files by size in a directory
$ qlmanage -p <file> # QuickLook preview from command-line
$ top -o vsize # why is my mac slow?
```

[Go to table of contents 🔼](#quick-links)

## Hotkeys

| Hotkey | Description |
|----------|-------------|
| <kbd>Ctrl</kbd>+<kbd>A</kbd> | Go to the beginning of the line you are currently typing on |
| <kbd>Ctrl</kbd>+<kbd>E</kbd> | Go to the end of the line you are currently typing on |
| <kbd>Ctrl</kbd>+<kbd>L</kbd> | Clears the Screen, similar to the clear command |
| <kbd>Ctrl</kbd>+<kbd>U</kbd> | Clears the line before the cursor position. If you are at the end of the line, clears the entire line. |
| <kbd>Ctrl</kbd>+<kbd>H</kbd> | Same as backspace |
| <kbd>Ctrl</kbd>+<kbd>R</kbd> | Lets you search through previously used commands |
| <kbd>Ctrl</kbd>+<kbd>C</kbd> | Kill whatever you are running |
| <kbd>Ctrl</kbd>+<kbd>D</kbd> | Exit the current shell |
| <kbd>Ctrl</kbd>+<kbd>Z</kbd> | Puts whatever you are running into a suspended background process. fg restores it. |
| <kbd>Ctrl</kbd>+<kbd>W</kbd> | Delete the word before the cursor |
| <kbd>Ctrl</kbd>+<kbd>K</kbd> | Clear the line after the cursor |
| <kbd>Ctrl</kbd>+<kbd>T</kbd> | Swap the last two characters before the cursor |
| <kbd>Ctrl</kbd>+<kbd>F</kbd> | Move cursor forward one character |
| <kbd>Ctrl</kbd>+<kbd>B</kbd> | Move cursor backward one character |
| <kbd>Esc</kbd>+<kbd>T</kbd> | Swap the last two words before the cursor |
| <kbd>Alt</kbd>+<kbd>T</kbd> | Same as <kbd>Esc</kbd> + <kbd>T</kbd> |
| <kbd>Alt</kbd>+<kbd>F</kbd> | Move cursor forward one word on the current line |
| <kbd>Alt</kbd>+<kbd>B</kbd> | Move cursor backward one word on the current line |
| <kbd>Esc</kbd>+<kbd>F</kbd> | Same as <kbd>Alt</kbd> + <kbd>F</kbd> |
| <kbd>Esc</kbd>+<kbd>B</kbd> | Same as <kbd>Alt</kbd> + <kbd>B</kbd> |
| <kbd>Alt</kbd>+<kbd>.</kbd> | Paste the last word of the most recently command |
| <kbd>Tab</kbd> | Auto-complete files and directory names |
[Go to table of contents 🔼](#quick-links)

## I can't remember these cryptic commands

You can always google or `man` the commands you are not familiar with. Or, checkout [tldr](https://github.com/tldr-pages/tldr), a collection of simplified and community-driven man pages.

[Go to table of contents 🔼](#quick-links)
