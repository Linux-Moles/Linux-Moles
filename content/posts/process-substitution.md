---
title: "Process Substitution"
date: 2019-04-24T21:25:10-04:00
draft: true
toc: false
images:
tags: 
  - process
  - substitution
  - multi
---


In the shell piping, the stdout of a command into the stdin is a powerful technique in the terminal. But, what happens if you need to pipe the stdout of multiple commands, for example comparing and sort text data? Let use an example of where process substitution can be used.


example:

```bash

  <(list)
or
  >(list)

```

Now let try view the lines unique to each of these two unsorted files with using process substitution.

```bash

> sort file1 | uniq >ex1
> sort file2 | uniq >ex2
> comm -3 tmp1 tmp2
        c
        d
        f
> rm ex1 ex2

```

as you can see both files needed to be created in order to compare, with process substitution we can do all this with one line


