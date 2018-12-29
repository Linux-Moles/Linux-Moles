---
title: "Graphical Tree File Folder"
date: 2018-12-26T21:05:08-05:00
featuredImg: ""
tags: 
  - grep
  - ls
  - sed
---


##  Graphical tree of sub-directories

This oneliner command is for a graphical tree of sub-directories, this is an excellent oneliner when you're in need to view the directories in a graphical format. The tree is a recursive directory listing command or program that produces a depth indented listing of files which not generally found on all Linux or Unix systems. The first Tree Unix utility was developed by Steve Baker which includes a verbose of feature and flag option. This one-liner is a quick fix for an alternative tree version for portable and easy use.

let break down how this oneliner is build by go deep with the command that is
being used.

### using `ls`

using `ls -R` does recursively list subdirectories encountered. this will give
every thing in directory by level of current one


```sh

root@19472dcaa9be:/var/log# ls -R
.:
alternatives.log  apt  bootstrap.log  btmp  dpkg.log  faillog  lastlog  tallylog  wtmp

./apt:
eipp.log.xz  history.log
```
### using `grep`

Now with the grep command, we grep all line that end with `:`. using the `$`we
grabbing all line with `:`. 


```sh

root@19472dcaa9be:/var/log# ls -R | grep ':$'
.:
./apt:
```

### using `sed`

using the `sed` command on the final pipe `|` we will filter out the needed
directories and add |- and additional - for each level of the directories it
sitting in. with `sed` the flag `-e` will append the editing commands specified 
by the command argument to the list of commands.

```sh

root@19472dcaa9be:/var# ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/ /' -e 's/-/|/'
 .
 |-backups
 |-cache
 |---apt
 |-----archives
 |-------partial
 |---debconf
 |---ldconfig
 |-lib
 |---apt
 |-----lists
 |-----mirrors
 |-------partial
 |-----periodic
 |---dpkg
 |-----alternatives
 |-----info
 |-----parts
 |-----triggers
 |-----updates
 |---misc
 |---pam
 |---systemd
 |-----deb-systemd-helper-enabled
 |-------timers.target.wants
 |-local
 |-log
 |---apt
 |-mail
 |-opt
 |-spool
 |-tmp

```

credit: unixmonkey842 [source](https://www.commandlinefu.com/commands/view/710/graphical-tree-of-sub-directories)

