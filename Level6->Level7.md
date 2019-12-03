### OverTheWire Bandit Wargame: [Level6-->Level7](https://overthewire.org/wargames/bandit/bandit7.html)

#### Level Goal

`The password for the next level is stored somewhere on the server and has all of the following properties:`

`owned by user bandit7`
`owned by group bandit6`
`33 bytes in size`

#### Guide

* For this level, I assume that you have already entered the `bandit6` system via SSH. If you are not in the `bandit6` system, please refer [level5->level6](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level5-%3ELevel6.md) guide to enter the `bandit6` system.

* When you try to list the files in the `root` directory of `bandit6` system, you will observe that there are no files.

* That is obvious as the problem statement clearly states that the file is store on the server somewhere. Also, the owner of the file is `bandit7` system. Therefore, it is not available on `bandit6` system.

* However, that file is being shared with a group called `bandit6` and our current system is a member of that group.

* We use the same `find` command here with the `user` and `-group` flags as parameters.

#### Solution

* Use the following commands to retreive the password to next level:

```shell
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -type f 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
bandit6@bandit:~$ 
```

* `2>/dev/null` is used to throw the output into a null device:
    > `2>` redirects the stderr to file
    > `/dev/null` is the null device. It takes any input you want and throws it away. It can be used to suppress any output.

* A more shorter way to execute this command in one line is:

```shell
cat `find / -user bandit7 -group bandit6 -size 33c -type f 2>/dev/null`
```

The password to Level7 is
```shell
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level7-%3ELevel8.md) level guide.