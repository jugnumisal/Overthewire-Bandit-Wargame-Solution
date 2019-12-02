### OverTheWire Bandit Wargame: [Level0-->Level1](https://overthewire.org/wargames/bandit/bandit1.html)

#### Level Goal

`The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.`

#### Guide

* For this level, I assume that you have already entered the `bandit0` system via SSH. If you are not in the `bandit0` system, please refer [level0](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level0.md) guide to enter the level0 system.

* Once you are in the system, use the `ls` command to find a readme file. This is the file that contains the password to level1. To open the file, use `cat` command.

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
bandit0@bandit:~$ 
```

The password to Level1 is
```shell
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```