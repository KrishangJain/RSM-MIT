# Linux Luminarium

## Module 2: Pondering Paths

### The Root

Solution: I invoked the /pwn program using its absolute path.

Terminal: 
```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{sLWIed6LhQWCu8hToZSJK59pRUB.QX4cTO0wiM1IzNxEzW}
```
Flag: 
pwn.college{sLWIed6LhQWCu8hToZSJK59pRUB.QX4cTO0wiM1IzNxEzW}

### Program and absolute paths

Solution: I executed the /challenge/run file using its absolute path.

Terminal: 
```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{8RkUx7cACrusO-40UcN4cZczyHT.QX1QTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{8RkUx7cACrusO-40UcN4cZczyHT.QX1QTN0wiM1IzNxEzW}

### Position thy self

Solution: Changed to the directory mentioned and from that directory executed /challenge/run

Terminal: 
```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /proc/142/fd directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /proc/142/fd
hacker@paths~position-thy-self:/proc/142/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gPop15IzIQ3pIbOv4nV79oFMp1W.QX2QTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{gPop15IzIQ3pIbOv4nV79oFMp1W.QX2QTN0wiM1IzNxEzW}

### Position elsewhere

Solution: Changed to the directory mentioned and from that directory executed /challenge/run

Terminal: 
```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /sys/kernel directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /sys/kernel
hacker@paths~position-elsewhere:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{kengyDXkPJgDCBZrBhpLQqHCP9N.QX3QTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{kengyDXkPJgDCBZrBhpLQqHCP9N.QX3QTN0wiM1IzNxEzW}

### implicit relative paths, from /

Solution: Changed to the / directory, from there, invoked the challenge/run relative path

Terminal: 
```bash
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{08Y5eTP-wHJKlTqoADgHkrSC1Cx.QX5QTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{08Y5eTP-wHJKlTqoADgHkrSC1Cx.QX5QTN0wiM1IzNxEzW}

### explicit relative paths, from /

Solution: Changed to the / directory, from there, invoked the ./challenge/run relative path

Terminal: 
```bash
hacker@paths~explicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oCRhBz3tXNE47i0Gp1LwsMqxd9a.QXwUTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{oCRhBz3tXNE47i0Gp1LwsMqxd9a.QXwUTN0wiM1IzNxEzW}

### implicit relative path

Solution: Changed to the /challenge directory from there, invoked the ./run relative path

Terminal: 
```bash
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{sgMB_ZBNl6EVvqvCEJJviGbn9Vg.QXxUTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{sgMB_ZBNl6EVvqvCEJJviGbn9Vg.QXxUTN0wiM1IzNxEzW}

### home sweet home

Solution: passed ~/l as an argument to /challenge/run. ~/l expands to /home/hacker. it creates a file 'l' at the location.

Terminal: 
```bash
hacker@paths~home-sweet-home:~$  /challenge/run ~/l
Writing the file to /home/hacker/l!
... and reading it back to you:
pwn.college{MsN2G60-5WOmb-hoKAG7_uoYvmS.QXzMDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{MsN2G60-5WOmb-hoKAG7_uoYvmS.QXzMDO0wiM1IzNxEzW}
