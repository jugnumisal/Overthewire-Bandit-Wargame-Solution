### OverTheWire Bandit Wargame: [Level3-->Level4](https://overthewire.org/wargames/bandit/bandit4.html)

#### Level Goal

`The password for the next level is stored in a hidden file in the inhere directory.`

#### Guide

* For this level, I assume that you have already entered the `bandit3` system via SSH. If you are not in the `bandit3` system, please refer [level2->level3](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level2-%3ELevel3.md) guide to enter the `bandit3` system.

* Until now, we have been working with finding the password in a file which was located in the `root` of the filesystem. But here, the file is saved inside a directory named "inhere" in the `root` of the filesystem.

* Linux provides various flags with the `ls` command. [Read here](http://nersp.nerdc.ufl.edu/~dicke3/nerspcs/ls.html) for detailed description of all the flags that can be used with `ls` command and their description.

* Here, we use the `-l` flag to display the mode, number of links, owner, group, size (in bytes), and time of last modification for each file. If the file is a special file, the size field contains the major and minor device numbers.

* To enter a particular directory, we use `cd` command followed by the name of the directory.

* Once you are inside the directory, again use the `ls -l` command and to your surprise, you will see `total 0` as the output. That means there are no files in the that directory.

* The problem statement itself mentions that the file is hidden in this directory. Hidden files cannot be listed using the `-l` flag. To display the list of all files including the hidden files in the current directory, we use the `-a` command. When you use the `-a` command, you will see a file with the name `.hidden`. Hidden files in linux start with `.`.

* To see the text in this file, use the `cat` command with the filename and you shall be able to see the text inside the hidden file which is the password to next level.

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit3@bandit:~$ ls -l
total 4
drwxr-xr-x 2 root root 4096 Oct 16  2018 inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -l
total 0
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden 
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
bandit3@bandit:~/inhere$ 
```

The password to Level4 is
```shell
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level4-%3ELevel5.md) level guide.