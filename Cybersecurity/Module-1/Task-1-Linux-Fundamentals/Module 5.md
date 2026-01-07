# Linux Luminarium

## Module 5: File Globbing

### Matching with *

Solution: used * to shorten the change directory command to 4 characters only.

Terminal: 
```bash
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{MXjojqSZ77B8SRE2uFWHfiQjfTI.QXxIDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{MXjojqSZ77B8SRE2uFWHfiQjfTI.QXxIDO0wiM1IzNxEzW}

### Matching with ?

Solution: replaced every c and l for the cd command with a ?

Terminal: 
```bash
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{YIRbVKBObk0-ZFZDFV5ihH2KFWy.QXyIDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{YIRbVKBObk0-ZFZDFV5ihH2KFWy.QXyIDO0wiM1IzNxEzW}

### Matching with []

Solution: changed directory then used file_[bash] to match all 4 files with 1 argument for the /challenge/run command.

Terminal: 
```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{gci0yB0BUSQxqhnywAZqmqkdMIW.QXzIDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{gci0yB0BUSQxqhnywAZqmqkdMIW.QXzIDO0wiM1IzNxEzW}

### Matching paths with []

Solution: used file_[bash] with the absolute path to match all 4 files as an argument to /challenge/run

Terminal: 
```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{owNw_4BHuDANpurc3ZXHYS8xkua.QX0IDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{owNw_4BHuDANpurc3ZXHYS8xkua.QX0IDO0wiM1IzNxEzW}

### Multiple globs

Solution: changed directory, ran /challenge/run with the only valid argument that captures every word containing the letter p which is ```*p*```.

Terminal: 
```bash
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{0oI6W3G4TXpGYLY2aIDTCdR9TL6.0lM3kjNxwiM1IzNxEzW}
```
Flag: 
pwn.college{0oI6W3G4TXpGYLY2aIDTCdR9TL6.0lM3kjNxwiM1IzNxEzW}

### Mixing globs

Solution: changed directory. checked all files. noticed all of them start with different letters of the alphabet. used the [cep]* glob as an argument to /challenge/run because it will check c,e,p as the first letters and match the correct files.

Terminal: 
```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      fantastic   kind        pwning     uplifting   zesty
beautiful    great       laughing    queenly    victorious
challenging  happy       magical     radiant    wonderful
delightful   incredible  nice        splendid   xenial
educational  jovial      optimistic  thrilling  youthful
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{gr_CZ6GQFYbNKMyWUg6xMwJ0x9D.QX1IDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{gr_CZ6GQFYbNKMyWUg6xMwJ0x9D.QX1IDO0wiM1IzNxEzW}

### Exclusionary globbing

Solution: changed directory then used [!pwn]* to exclude all files that start with p,w,n.

Terminal: 
```bash
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{Ueapg3s-N8rSz08zF3CSNGKutM9.QX2IDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{Ueapg3s-N8rSz08zF3CSNGKutM9.QX2IDO0wiM1IzNxEzW}

### Tab completion

Solution: used tab completion after typing pw to autocomplete it and received the flag

Terminal: 
```bash
hacker@globbing~tab-completion:/challenge$ cat pwncollege​
pwn.college{E3HbYvRRtA7Fd3PV2K-iRzf0sf0.0FN0EzNxwiM1IzNxEzW}
```
Flag: 
pwn.college{E3HbYvRRtA7Fd3PV2K-iRzf0sf0.0FN0EzNxwiM1IzNxEzW}

### Multiple options for tab completion

Solution: used double tab to display all the options when cat p was written, started checking manually till flag found

Terminal: 
```bash
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn-the-planet
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwncollege-flag
pwn.college{UeUEFTHcniLiF3ktFr2JWoLwI4p.0lN0EzNxwiM1IzNxEzW}
```
Flag: 
pwn.college{UeUEFTHcniLiF3ktFr2JWoLwI4p.0lN0EzNxwiM1IzNxEzW}

### Tab completion on commands

Solution: typed pwnc and used tab completion to autocomplete the command.

Terminal: 
```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-28372
Correct! Here is your flag:
pwn.college{g0PFZcgO75U8OGCByvQhCSyYhS-.0VN0EzNxwiM1IzNxEzW}
```
Flag: 
pwn.college{g0PFZcgO75U8OGCByvQhCSyYhS-.0VN0EzNxwiM1IzNxEzW}
