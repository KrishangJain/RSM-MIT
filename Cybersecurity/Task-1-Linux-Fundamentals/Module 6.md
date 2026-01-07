# Linux Luminarium

## Module 6: Practicing Piping

### Redirecting output

Solution: redirected the output of echo PWN to the file COLLEGE

Terminal: 
```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{QEUdMH2JFEpcRrko_7-l9z2MhP0.QX0YTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{QEUdMH2JFEpcRrko_7-l9z2MhP0.QX0YTN0wiM1IzNxEzW}

### Redirecting more output

Solution: redirected output of /challenge/run to file myflag and used cat to read it.

Terminal: 
```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{kMdYUa2bHlov08rtDTUyi_RDPRx.QX1YTN0wiM1IzNxEzW}

```
Flag: 
pwn.college{kMdYUa2bHlov08rtDTUyi_RDPRx.QX1YTN0wiM1IzNxEzW}

### Appending output

Solution: appended the ~/the-flag file with the output of /challenge/run so that the first half of the flag isn't wiped and the second half is added.

Terminal: 
```bash
hacker@piping~appending-output:~$ /challenge/run >> the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag
 |
\|/ This is the first half:
 v
pwn.college{IG_NZZz9QQrjvMXIIAxnO9Sk10o.QX3ATO0wiM1IzNxEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```
Flag: 
pwn.college{IG_NZZz9QQrjvMXIIAxnO9Sk10o.QX3ATO0wiM1IzNxEzW}

### Redirecting errors

Solution: redirected output of /challenge/run to myflag and errors to instructions. used cat to read both.

Terminal: 
```bash
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{QCVrj20rB8jhiAfJ4Fi55eseKzQ.QX3YTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{QCVrj20rB8jhiAfJ4Fi55eseKzQ.QX3YTN0wiM1IzNxEzW}

### Redirecting input

Solution: used echo to write COLLEGE into PWN. passed PWN as input to /challenge/run using <

Terminal: 
```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{EzK1g0R_ZCPKSNZ3pwBHZ9ZvegO.QXwcTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{EzK1g0R_ZCPKSNZ3pwBHZ9ZvegO.QXwcTN0wiM1IzNxEzW}

### Grepping stored results

Solution: redirected output of /challenge/flag to /tmp/data.txt. used grep on the file with the argument pwn.college to get the flag

Terminal: 
```bash
hacker@piping~grepping-stored-results:~$ /challenge/flag > /tmp/data.txt
bash: /challenge/flag: No such file or directory
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{8mCXDm_OFiDEaXOP7x_ij2tMTxN.QX4EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{8mCXDm_OFiDEaXOP7x_ij2tMTxN.QX4EDO0wiM1IzNxEzW}

### Grepping live output

Solution: used | to redirect output of /challenge/run directly as input to grep command with the argument pwn.college

Terminal: 
```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/qjsj5vnbfpbg6r7jhd7znfgmcy0arn8n-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{UeT00-J_eMk_i4lpX8oGfpNGj0Y.QX5EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{UeT00-J_eMk_i4lpX8oGfpNGj0Y.QX5EDO0wiM1IzNxEzW}

### Grepping errors

Solution: used 2>&1 to combine error and output and passed that to grep pwn.college directly using |

Terminal: 
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/qjsj5vnbfpbg6r7jhd7znfgmcy0arn8n-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{0bW5uZDwMhTFVOrhkoTTYp141LQ.QX1ATO0wiM1IzNxEzW}
```
Flag: 
pwn.college{0bW5uZDwMhTFVOrhkoTTYp141LQ.QX1ATO0wiM1IzNxEzW}

### Filtering with grep -v

Solution: used -v argument with grep to filter out the word decoy and get the flag

Terminal: 
```bash
hacker@piping~filtering-with-grep-v:~$  /challenge/run | grep -v "DECOY"
pwn.college{kIfRKLFZ5mmXKMZ-CnY_ZEMpLUV.0FOxEzNxwiM1IzNxEzW}
```
Flag: 
pwn.college{kIfRKLFZ5mmXKMZ-CnY_ZEMpLUV.0FOxEzNxwiM1IzNxEzW}

### Filtering with sed

Solution: used the syntax sed "s/oldword/newword/g", kept newword empty as it was mentioned in the description that the FAKEFLAG word appears between characters

Terminal: 
```bash
hacker@piping~filtering-with-sed:~$ /challenge/run | sed "s/FAKEFLAG//g"
pwn.college{o6qZ_TE98A7ouXHH4Ir53wvYwKj.01NxQTMywiM1IzNxEzW}
```
Flag: 
pwn.college{o6qZ_TE98A7ouXHH4Ir53wvYwKj.01NxQTMywiM1IzNxEzW}

### Duplicating piped data with tee

Solution: used tee output to duplicate the output of /challenge/pwn before it is passed as input to /challenge/college. used cat on it to find the correct argument to be passed for it to work.

Terminal: 
```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee output | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat output
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "sejmaer_"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret sejmaer_ | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{sejmaer_pGtmm3anKfwF9z6TGDH.QXxITO0wiM1IzNxEzW}
```
Flag: 
pwn.college{sejmaer_pGtmm3anKfwF9z6TGDH.QXxITO0wiM1IzNxEzW}

### Process substitution for input

Solution: used diff with process subsitution for both of its inputs, put the output of the commands as input to diff.

Terminal: 
```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
0a1
> pwn.college{QulSfx2_X_MLJzqaLMkbkxK1xP9.0lNwMDOxwiM1IzNxEzW}
```
Flag: 
pwn.college{QulSfx2_X_MLJzqaLMkbkxK1xP9.0lNwMDOxwiM1IzNxEzW}

### Writing to multiple programs

Solution: | passes the output of /challenge/hack to tee which duplicates the data and sends it as input to the /challenge/the and /challenge/planet commands

Terminal: 
```bash
hacker@piping~writing-to-multiple-programs:~$  /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
110482573492022527
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{w4kcWlVccPsZjE_LyaZeuVDIDXf.QXwgDN1wiM1IzNxEzW}
```
Flag: 
pwn.college{w4kcWlVccPsZjE_LyaZeuVDIDXf.QXwgDN1wiM1IzNxEzW}

### Split-piping stderr and stdout

Solution: redirected output of /challenge/hack, sent output to /challenge/planet and errors to /challenge/the as inputs using process substitution

Terminal: 
```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{E62mLYPf2NWTl334wnOT_kXw3jZ.QXxQDM2wiM1IzNxEzW}
```
Flag: 
pwn.college{E62mLYPf2NWTl334wnOT_kXw3jZ.QXxQDM2wiM1IzNxEzW}

### Named pipes

Solution: redirected stdout of /challenge/run to the fifo, which resulted in a block. used another terminal window to clear the block and get the flag

Terminal: 
```bash
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
(switching to a different terminal instance)
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{gRITsv2b1a9f3ZNJQHmSBdnklFN.01MzMDOxwiM1IzNxEzW}
```
Flag: 
pwn.college{gRITsv2b1a9f3ZNJQHmSBdnklFN.01MzMDOxwiM1IzNxEzW}
