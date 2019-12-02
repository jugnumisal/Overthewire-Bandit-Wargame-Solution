### OverTheWire Bandit Wargame: [Level1-->Level2](https://overthewire.org/wargames/bandit/bandit2.html)

#### Level Goal

`The password for the next level is stored in a file called - located in the home directory`

#### Guide

* For this level, I assume that you have already entered the `bandit1` system via SSH. If you are not in the `bandit1` system, please refer [level0->level1](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level0-%3ELevel1.md) guide to enter the `bandit1` system.

* In this level, there is a file with the name `-`. Such `-` (dash) files cannot be accessed directly using `cat` command as `-` is mainly refered as a stdin or stdout. For further details on such dash (-) file please [read](https://linux-tips.com/t/dashed-filename-in-linux/188).

* To access the text in this file, we need to give the file `-` as an input to the `cat` command. [When you use the redirect with standard input ‘<‘ (less than symbol), it uses the `filename`  as a input for a command and output will be shown in a terminal.](https://www.tecmint.com/13-basic-cat-command-examples-in-linux/)

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat < -
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
bandit1@bandit:~$ 
```

The password to Level2 is
```shell
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

Go to [next]() level guide.