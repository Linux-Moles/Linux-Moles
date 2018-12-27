---
title: "Graphical Tree File Folder"
date: 2018-12-26T21:05:08-05:00
draft: true
featuredImg: ""
tags: 
  - grep
  - ls
  - sed
---


#  Graphical tree of sub-directories

This oneliner command is for graphical tree of sub-directories, this is a great
oneline when your in a need to view the directories in a graphical format. The
tree is a recursive directory listing command or program that produces a
depth-indented listing of files which not normally found on all Linux or Unix
systems. The the original Tree Unix utility was developed by Steve Baker. which
includes a verbose of feature and flag option. This onliner is a quick fix for
a tree alternavite version for portable and easy use.

let break down how this oneliner is build by go deep with the command that is
being used.




### final commandline

`ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/ /' -e 's/-/|/'`

credit: unixmonkey842 [source](https://www.commandlinefu.com/commands/view/710/graphical-tree-of-sub-directories)

