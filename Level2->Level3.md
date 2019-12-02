### OverTheWire Bandit Wargame: [Level2-->Level3](https://overthewire.org/wargames/bandit/bandit3.html)

#### Level Goal

`The password for the next level is stored in a file called "spaces in this filename" located in the home directory`

#### Guide

* For this level, I assume that you have already entered the `bandit2` system via SSH. If you are not in the `bandit2` system, please refer [level1->level2](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level1-%3ELevel2.md) guide to enter the `bandit2` system.

* Here, the filename is not just 1 word, it a sentence (`spaces in this filename`). To select the files with names longer than one word and with spaces in it, we use the backslash (`\`) after each word of the filename. For example, if the name of the file is "This is my file" you can access it using the command `cat This\ is\ my\ file`.

*Note:* A simple way to avoid typing the complete command and the filename, you can always use the `Tab` button on your keyboard after typing the initial letters of your filename and the linux will auto-complete your filenamet with the matching available options in the filesystem.

#### Solution

Use the following commands to retreive the password to next level:

```shell
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
bandit2@bandit:~$ 
```

The password to Level3 is
```shell
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```

Go to [next](https://github.com/jugnumisal/Overthewire-Bandit-Wargame-Solution/blob/master/Level3-%3ELevel4.md) level guide.