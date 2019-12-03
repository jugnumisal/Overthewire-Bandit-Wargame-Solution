### OverTheWire Bandit Wargame: [Level7-->Level8](https://overthewire.org/wargames/bandit/bandit8.html)

#### Level Goal

`The password for the next level is stored in the file data.txt next to the word millionth`

#### Guide

* For this level, I assume that you have already entered the `bandit7` system via SSH. If you are not in the `bandit7` system, please refer [level6>level7](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level6-%3ELevel7.md) guide to enter the `bandit7` system.

* This is a pretty simple and straightforward problem if you are familiarizee with the `grep` command.

* When you `cat` the contents of the data.txt file, it prints the contents of the file and since the file contains millions of strings it is really hard to find the desired text in the file.

* Linux provides a special operator `|` called the "pipe" which is used as an extension to a command. Any command after the pipe(|) is executed after the previous command and the output of the previous command is passed as an input to the next command.

* [Here](https://ss64.com/bash/grep.html) is a documentation on "grep" command in Linux.
 
#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ cat data.txt | grep "millionth"
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
bandit7@bandit:~$ 
```

The password to Level8 is
```shell
cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level8-%3ELevel9.md) level guide.