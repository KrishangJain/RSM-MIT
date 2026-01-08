# Linux Luminarium

## Module 9: Processes and Jobs

### Listing Processes

Solution: used ps aux to see all processes and saw the randomly named file and ran it.

Terminal: 
```bash
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   21:45   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-works
root           7  0.0  0.0 231708  2560 ?        S    21:45   0:00 /run/dojo/bin/sleep 6h
root         134  0.0  0.0   4132  2560 ?        S    21:45   0:00 /challenge/5819-run-3456
root         137  0.0  0.0   2744  1600 ?        S    21:45   0:00 sleep 6h
hacker       148  0.0  0.0  36972 22080 ?        Sl   21:45   0:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.
hacker       162  0.0  0.0 231576  3520 pts/0    Ss   21:45   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       168  0.0  0.0 231940  4160 pts/0    S    21:45   0:00 /run/dojo/bin/bash --login
hacker       186  0.0  0.0 231940  4160 pts/1    Ss+  21:50   0:00 /run/dojo/bin/bash --login
hacker       196  0.0  0.0 233600  3840 pts/0    R+   21:53   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/5819-run-3456
Yahaha, you found me! Here is your flag:
pwn.college{scIV2dtJe0Dfs56rpUoBAhxHEBk.QX4MDO0wiM1IzNxEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```
Flag: 
pwn.college{scIV2dtJe0Dfs56rpUoBAhxHEBk.QX4MDO0wiM1IzNxEzW}

### Killing Processes

Solution: used grep to find the dont run process, killed it using its PID.

Terminal: 
```bash
hacker@processes~killing-processes:~$ ps aux | grep dont
hacker       138  0.0  0.0 231576  3520 ?        Ss   21:55   0:00 /challenge/dont_run
hacker       180  0.0  0.0 230696  2560 pts/0    S+   21:56   0:00 grep --color=auto dont
hacker@processes~killing-processes:~$ kill 138
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{40f4eJmR2A75r-HR8twIpI06qbr.QXyQDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{40f4eJmR2A75r-HR8twIpI06qbr.QXyQDO0wiM1IzNxEzW}

### Interrupting Processes

Solution: used ctrl+c interrupt.

Terminal: 
```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{EdRvs10isn5VzS8oDHQrVQoq5hl.QXzQDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{EdRvs10isn5VzS8oDHQrVQoq5hl.QXzQDO0wiM1IzNxEzW}

### Killing Misbehaving Processes

Solution: used grep to find and kill to kill the process. 

Terminal: 
```bash
hacker@processes~killing-misbehaving-processes:~$ ps aux | grep decoy
root         141  0.0  0.0   5204  3520 ?        S    21:59   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       144  0.0  0.0  13516  9280 ?        Ss   21:59   0:00 /usr/bin/python /challenge/decoy
hacker       190  0.0  0.0 230696  2560 pts/0    S+   22:00   0:00 grep --color=auto decoy
hacker@processes~killing-misbehaving-processes:~$ kill 144
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{YjY_2bXrQho-A6vDY3Am32aqN27.0FNzMDOxwiM1IzNxEzW}
```
Flag: 
pwn.college{YjY_2bXrQho-A6vDY3Am32aqN27.0FNzMDOxwiM1IzNxEzW}

### Suspending Processes

Solution: used run twice to run it a second time while suspended.

Terminal: 
```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         163     131  0 22:06 pts/0    00:00:00 bash /challenge/run
root         165     163  0 22:06 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         163     131  0 22:06 pts/0    00:00:00 bash /challenge/run
root         177     131  0 22:06 pts/0    00:00:00 bash /challenge/run
root         179     177  0 22:06 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{gMA7XWFZzm6t1O1HjiWatmpng6k.QX1QDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{gMA7XWFZzm6t1O1HjiWatmpng6k.QX1QDO0wiM1IzNxEzW}

### Resuming Processes

Solution: used fg to resume run.

Terminal: 
```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{Yhjp9Pur9BUZ-rGLtHwWvWm243s.QX2QDO0wiM1IzNxEzW}
Don't forget to press Enter to quit me!

Goodbye!
```
Flag: 
pwn.college{Yhjp9Pur9BUZ-rGLtHwWvWm243s.QX2QDO0wiM1IzNxEzW}

### Backgrounding Processes

Solution: used run, bg and interrupt.

Terminal: 
```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         163 S+   bash /challenge/run
root         165 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         163 S    bash /challenge/run
root         173 S    sleep 6h
root         174 S+   bash /challenge/run
root         176 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{Q_64DAqAHibwZQ5ijZSS2PCyKMh.QX3QDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{Q_64DAqAHibwZQ5ijZSS2PCyKMh.QX3QDO0wiM1IzNxEzW}

### Foregrounding Processes

Solution: used bg, fg and run.

Terminal: 
```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{ENyaFr2TNhAbpRAVbvgqFcdp4rh.QX4QDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{ENyaFr2TNhAbpRAVbvgqFcdp4rh.QX4QDO0wiM1IzNxEzW}

### Starting Backgrounded Processes

Solution: used & to start a backgrounded process.

Terminal: 
```bash
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{0HAClNMdU0TtlAC68tAucLIYdwB.QX5QDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{0HAClNMdU0TtlAC68tAucLIYdwB.QX5QDO0wiM1IzNxEzW}

### Process Exit Codes

Solution: used echo $? to find error code of most recent process.

Terminal: 
```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
22
hacker@processes~process-exit-codes:~$ /challenge/submit-code 22
CORRECT! Here is your flag:
pwn.college{MhmQUcYVzOS3cM44xohEiHKc9k4.QX5YDO1wiM1IzNxEzW}
```
Flag: 
pwn.college{MhmQUcYVzOS3cM44xohEiHKc9k4.QX5YDO1wiM1IzNxEzW}