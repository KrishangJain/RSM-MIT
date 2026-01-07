# Linux Luminarium

## Module 10: Untangling Users

### Becoming root with su

Solution: used su then entered pass, navigated to directory and read flag.

Terminal: 
```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# cd
root@users~becoming-root-with-su:~# cd ..
root@users~becoming-root-with-su:/# cat flag
pwn.college{wbOhtL_tJD0zkeNidLXMK_cMqP8.QX1UDN1wiM1IzNxEzW}
```
Flag: 
pwn.college{wbOhtL_tJD0zkeNidLXMK_cMqP8.QX1UDN1wiM1IzNxEzW}

### Other users with su

Solution: used su with arg zardus as user, entered password

Terminal: 
```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{Ew872NC8cxWzIx6mbcq75vVMRTu.QX2UDN1wiM1IzNxEzW}
```
Flag: 
pwn.college{Ew872NC8cxWzIx6mbcq75vVMRTu.QX2UDN1wiM1IzNxEzW}

### Cracking passwords

Solution: used john to crack pass and then logged in as zardus

Terminal: 
```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04866g/s 283.3p/s 283.3c/s 283.3C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{Qpz8A1gGKgvRnAj5AYfd3NrPNnI.QX3UDN1wiM1IzNxEzW}
```
Flag: 
pwn.college{Qpz8A1gGKgvRnAj5AYfd3NrPNnI.QX3UDN1wiM1IzNxEzW}

### Using sudo

Solution: used sudo to cat flag 

Terminal: 
```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{UARkSFA7zcRA9MgXdQrRu3EWNg6.QX4UDN1wiM1IzNxEzW}
```
Flag: 
pwn.college{UARkSFA7zcRA9MgXdQrRu3EWNg6.QX4UDN1wiM1IzNxEzW}