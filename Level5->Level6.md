### OverTheWire Bandit Wargame: [Level5-->Level6](https://overthewire.org/wargames/bandit/bandit6.html)

#### Level Goal

`The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:`

1. `human-readable`
2. `1033 bytes in size`
3. `not executable`

#### Guide

* For this level, I assume that you have already entered the `bandit5` system via SSH. If you are not in the `bandit5` system, please refer [level4->level5](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level4-%3ELevel5.md) guide to enter the `bandit5` system.

* Here, when you explore the filesystem in the `root` directory, you see that there is a directory named "inhere" followed by 20 other directories.

* Each of these directories consists of several files, executable files and hidden files.

* Finding for our password file by recursively entering each directory and checking the contents of it is a very cumbersome job.

* To avoid such situation, Linux provides a command `find` to find anything in the filesystem.

* To know how to use `find` command, type `man find` in your terminal and it will show you the syntax and the related flags and options that can be used with the `find` command.

#### Solution

* Use the following commands to retreive the password to next level:

```shell
bandit5@bandit:~$ ls -l
total 4
drwxr-x--- 22 root bandit5 4096 Oct 16  2018 inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -l
total 80
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere00
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere01
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere02
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere03
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere04
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere05
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere06
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere07
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere08
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere09
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere10
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere11
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere12
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere13
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere14
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere15
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere16
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere17
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere18
drwxr-x--- 2 root bandit5 4096 Oct 16  2018 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
* Following is the explanation of each flag used in the find command:
    * `.` after the find means that the find should be executed in the current directory.
    * `-type` flag is used to mention the type of the file that you are searching for. Here we are searching for a file, hence `f`.
    * `-size` flag is used to mention how much is the size of file that we are searching for. We are given that the file size is 1033 bytes, hence `1033c` where c represents bytes.
    * Finally, we use `! -executable` to give the argument that the file is a non-executable type file.

The password to Level6 is
```shell
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level6-%3ELevel7.md) level guide.