### OverTheWire Bandit Wargame: [Level8-->Level9](https://overthewire.org/wargames/bandit/bandit9.html)

#### Level Goal

`The password for the next level is stored in the file data.txt and is the only line of text that occurs only once`

#### Guide

* For this level, I assume that you have already entered the `bandit8` system via SSH. If you are not in the `bandit8` system, please refer [level7->level8](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level7-%3ELevel8.md) guide to enter the `bandit8` system.

* To approach this problem, you must first `sort` the data which place all identical lines next to each other. To implement this, Linux provides a command `sort`. Refer [sort](http://man7.org/linux/man-pages/man1/sort.1.html) man page for documentation.

* Once that is complete, you use the `uniq` command with the `-u` flag to only display strings that are not duplicated. Refer [uniq](http://man7.org/linux/man-pages/man1/uniq.1.html) man page for documentation.

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit8@bandit:~$ 
```

The password to Level9 is

```shell
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level9-%3ELevel10.md) level guide.