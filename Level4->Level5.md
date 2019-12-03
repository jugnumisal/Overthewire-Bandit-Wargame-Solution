### OverTheWire Bandit Wargame: [Level4-->Level5](https://overthewire.org/wargames/bandit/bandit5.html)

#### Level Goal

`The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.`

#### Guide

* For this level, I assume that you have already entered the `bandit4` system via SSH. If you are not in the `bandit4` system, please refer [level3->level4]() guide to enter the `bandit4` system.

* We have to find a file in human-readable format in the "inhere" directory. So we can use the `file` command that will show the type of the content inside the file. Please refer this [page](https://shapeshed.com/unix-file/) to know the in-depth use of file command in Linux.


#### Solution

* Use the following commands to retreive the password to next level:

```shell
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ file inhere/*
inhere/-file00: data
inhere/-file01: data
inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: data
bandit4@bandit:~$ cat inhere/-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
bandit4@bandit:~$ 
```
* Here, when we use `/*` after the file, it asks the Linux to show all the files in the inhere directory with their file types.

* Only the `-file07` is of type ASCII text. Hence, that is our desired password file. 

The password to Level5 is
```shell
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

Go to [next]() level guide.