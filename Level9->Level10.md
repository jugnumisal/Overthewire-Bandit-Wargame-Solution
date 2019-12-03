### OverTheWire Bandit Wargame: [Level9-->Level10](https://overthewire.org/wargames/bandit/bandit10.html)

#### Level Goal

`The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.`

#### Guide

* For this level, I assume that you have already entered the `bandit9` system via SSH. If you are not in the `bandit9` system, please refer [level8->level9]() guide to enter the `bandit9` system.

* The file `data.txt` consists of many human-readable strings. Some of them begin with "=". To approach this problem, use the `strings` command followed by `grep` to limit the search to string starting with "=". Refer [strings](http://man7.org/linux/man-pages/man1/strings.1.html) for understanding its use.

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep "="
2========== the
========== password
>t=	yP
rV~dHm=
========== isa
=FQ?P\U
=	F[
pb=x
J;m=
=)$=
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
iv8!=
bandit9@bandit:~$ 
```

The password to Level9 is

```shell
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

Go to [next]() level guide.