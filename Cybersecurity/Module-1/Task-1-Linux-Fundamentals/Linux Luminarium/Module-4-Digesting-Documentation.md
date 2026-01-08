# Linux Luminarium

## Module 4: Digesting Documentation

### Learning From Documentation

Solution: passed --giveflag as an argument to /challenge/challenge 

Terminal: 
```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{AWTVIXRtJvC2umGOdLRjTbW-T4X.QX0ITO0wiM1IzNxEzW}
```
Flag: 
pwn.college{AWTVIXRtJvC2umGOdLRjTbW-T4X.QX0ITO0wiM1IzNxEzW}

### Learning Complex Usage

Solution: passed /flag as an argument to --printfile argument of the /challenge/challenge command 

Terminal: 
```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{UzxSaIqkBWVNBbu8g7ht0oTFX0s.QX1ITO0wiM1IzNxEzW}
```
Flag: 
pwn.college{UzxSaIqkBWVNBbu8g7ht0oTFX0s.QX1ITO0wiM1IzNxEzW}

### Reading Manuals

Solution: read the manual for challenge. found that passing 400 as an argument to the --gykazf argument of the /challenge/challenge command will print the flag
Terminal: 
```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge  --gykazf 400
Correct usage! Your flag: pwn.college{MgyVLAVWOOkUa4CzHfCRAJa-vkv.QX0EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{MgyVLAVWOOkUa4CzHfCRAJa-vkv.QX0EDO0wiM1IzNxEzW}

### Searching Manuals

Solution: read the manual. searched with /flag and found that passing --geqz as an argument prints the flag

Terminal: 
```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --geqz
Initializing...
Correct usage! Your flag: pwn.college{YC8gFkBcADtOMM-jub8hGodb8D-.QX1EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{YC8gFkBcADtOMM-jub8hGodb8D-.QX1EDO0wiM1IzNxEzW}

### Searching For Manuals

Solution: searched man man, learned about -k to search with keywords. used it to find the randomly named page. used man to check the manual for that page. followed the manual to get the flag.

Terminal: 
```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
wcavhncwiz (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man wcavhncwiz
hacker@man~searching-for-manuals:~$ /challenge/challenge --wcavhn 613
Correct usage! Your flag: pwn.college{EMAwHVc6O13aFTvPhYSC6n5ONcB.QX2EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{EMAwHVc6O13aFTvPhYSC6n5ONcB.QX2EDO0wiM1IzNxEzW}

### Helpful Programs

Solution: checked --help to find -p prints the value we need to pass to -g to get the flag

Terminal: 
```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give
                        you the flag
hacker@man~helpful-programs:~$  /challenge/challenge -p
The secret value is: 644
hacker@man~helpful-programs:~$  /challenge/challenge -g 644
Correct usage! Your flag: pwn.college{MegbnIj6nUPd4Fkac49XaPeQdw-.QX3IDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{MegbnIj6nUPd4Fkac49XaPeQdw-.QX3IDO0wiM1IzNxEzW}

### Help for Builtins

Solution: checked the help page for the challenge command. passed the --secret argument to the challenge command with the secret argument mentioned.

Terminal: 
```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "AUuxO9R0".
hacker@man~help-for-builtins:~$ challenge --secret AUuxO9R0
Correct! Here is your flag!
pwn.college{AUuxO9R0bbP7yPUuGvLIVVtz2P1.QX0ETO0wiM1IzNxEzW}
```
Flag: 
pwn.college{AUuxO9R0bbP7yPUuGvLIVVtz2P1.QX0ETO0wiM1IzNxEzW}
