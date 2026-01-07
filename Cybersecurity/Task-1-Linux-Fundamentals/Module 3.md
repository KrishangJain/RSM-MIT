# Linux Luminarium

## Module 3: Comprehending Commands

### cat: not the pet, but the command!

Solution: used cat flag 

Terminal: 
```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{Mb_udK6Qrqw43Ww3Y1DVCHXtQ0R.QXxcTN0wiM1IzNxEzW}
```
Flag: 
pwn.college{Mb_udK6Qrqw43Ww3Y1DVCHXtQ0R.QXxcTN0wiM1IzNxEzW}

### catting absolute paths

Solution: used cat /flag, the absolute path as it is not in the home directory

Terminal: 
```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{c12XkR1b-UPeomnEy08kjSuduES.QX5ETO0wiM1IzNxEzW}
```
Flag: 
pwn.college{c12XkR1b-UPeomnEy08kjSuduES.QX5ETO0wiM1IzNxEzW}

### more catting practise

Solution: used the /lib/ssl/flag absolute path as an argument for cat

Terminal: 
```bash
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /lib/ssl/flag. Go cat it out **without** cding into that directory!
hacker@commands~more-catting-practice:~$ cat /lib/ssl/flag
pwn.college{g62wwFotwgqPSGzB17matbDPFz6.QXwITO0wiM1IzNxEzW}
```
Flag: 
pwn.college{g62wwFotwgqPSGzB17matbDPFz6.QXwITO0wiM1IzNxEzW}

### grepping for a needle in a haystack

Solution: used grep on the file /challenge/data.txt with the argument pwn.college as we know every flag starts with that

Terminal: 
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{MdGnXsQN4szq_ZLJ8tRiPx1UNyE.QX3EDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{MdGnXsQN4szq_ZLJ8tRiPx1UNyE.QX3EDO0wiM1IzNxEzW}

### comparing files

Solution: used diff command to search for the 1 different line

Terminal: 
```bash
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
49a50
> pwn.college{wu1uxcd68LX1ReRuFCKPkZ7qQYQ.01MwMDOxwiM1IzNxEzW}
```
Flag: 
pwn.college{wu1uxcd68LX1ReRuFCKPkZ7qQYQ.01MwMDOxwiM1IzNxEzW}

### listing files

Solution: navigated to /challenge. checked contents with ls. ran the file found using ./24221-renamed-run-6036

Terminal: 
```bash
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
24221-renamed-run-6036  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ ./24221-renamed-run-6036
Yahaha, you found me! Here is your flag:
pwn.college{AlrORUp5RJcSQnZxxpH92oMN2_T.QX4IDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{AlrORUp5RJcSQnZxxpH92oMN2_T.QX4IDO0wiM1IzNxEzW}

### touching files

Solution: created pwn and college files in the pwn directory

Terminal: 
```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{IpsmplqAWmmYMUcyX5kdrzeZ7H1.QXwMDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{IpsmplqAWmmYMUcyX5kdrzeZ7H1.QXwMDO0wiM1IzNxEzW}

### removing files

Solution: used rm to delete the delete_me file

Terminal: 
```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{04WbzWSnh6K9bo5vEIDt858q8Cl.QX2kDM1wiM1IzNxEzW}
```
Flag: 
pwn.college{04WbzWSnh6K9bo5vEIDt858q8Cl.QX2kDM1wiM1IzNxEzW}

### moving files

Solution: used mv command with absolute paths to move flag file to another file in a different directory

Terminal: 
```bash
hacker@commands~moving-files:/$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:/$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{MLe0T_IJmYeSa5hpNkPu0xwm4VC.0VOxEzNxwiM1IzNxEzW}
```
Flag: 
pwn.college{MLe0T_IJmYeSa5hpNkPu0xwm4VC.0VOxEzNxwiM1IzNxEzW}

### copying files

Solution: used cp instead of mv to retain the original file

Terminal: 
```bash
hacker@commands~copying-files:/$ cp flag tmp/hack-the-planet
Correct! Performing 'cp flag tmp/hack-the-planet'.
hacker@commands~copying-files:/$ /challenge/check
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0em4quTFfwWKmTp3Dkq_y8Pvh8g.0lNxQTMywiM1IzNxEzW}
```
Flag: 
pwn.college{0em4quTFfwWKmTp3Dkq_y8Pvh8g.0lNxQTMywiM1IzNxEzW}

### hidden files

Solution: searched for hidden files in /. read the file using cat

Terminal: 
```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.                     bin        etc    lib64   nix   run   tmp
..                    boot       home   libx32  opt   sbin  usr
.dockerenv            challenge  lib    media   proc  srv   var
.flag-20171819627710  dev        lib32  mnt     root  sys
hacker@commands~hidden-files:/$ cat .flag-20171819627710
pwn.college{IAc7EJwpd10Ww25aKLp0FiHKWH_.QXwUDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{IAc7EJwpd10Ww25aKLp0FiHKWH_.QXwUDO0wiM1IzNxEzW}

### An Epic Filesystem Quest

Solution: searched for hidden files in /. read the file using cat

Terminal: 
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
CLUE  challenge  flag  lib32   media  opt   run   sys  var
bin   dev        home  lib64   mnt    proc  sbin  tmp
boot  etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ cat CLUE
Yahaha, you found me!
The next clue is in: /etc/dpkg/dpkg.cfg.d

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/$ ls /etc/dpkg/dpkg.cfg.d
SNIPPET-TRAPPED  docker-apt-speedup  pkg-config-hook-config
hacker@commands~an-epic-filesystem-quest:/$ cat /etc/dpkg/dpkg.cfg.d/SNIPPET-TRAPPED
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/werkzeug

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/werkzeug
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/werkzeug$ ls
MESSAGE       datastructures  local.py    security.py  user_agent.py
__init__.py   debug           middleware  serving.py   utils.py
__pycache__   exceptions.py   py.typed    test.py      wrappers
_internal.py  formparser.py   routing     testapp.py   wsgi.py
_reloader.py  http.py         sansio      urls.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/werkzeug$ cat MESSAGE
Great sleuthing!
The next clue is in: /usr/share/maxima-sage/5.42.2/share/cobyla
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/werkzeug$ cd /usr/share/maxima-sage/5.42.2/share/cobyla
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/cobyla$ ls
HINT                      cobyla-lisp.system   lisp
bf-cobyla-interface.lisp  cobyla-package.lisp  load-bf-cobyla.lisp
bf_fmin_cobyla.demo       cobyla.system        load-cobyla.lisp
bf_fmin_cobyla.mac        ex                   rtest_cobyla.mac
cobyla-interface.lisp     fmin_cobyla.mac
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/cobyla$ cat HINT
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/rust/cryptography-cffi

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/maxima-sage/5.42.2/share/cobyla$ cd /usr/local/lib/python3.8/dist-packages/rust/cryptography-cffi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/rust/cryptography-cffi$ ls -a
.  ..  .DOSSIER  Cargo.toml
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/rust/cryptography-cffi$ cat .DOSSIER
Great sleuthing!
The next clue is in: /usr/share/jmol/appletweb
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/rust/cryptography-cffi$ cd /usr/share/jmol/appletweb
hacker@commands~an-epic-filesystem-quest:/usr/share/jmol/appletweb$ ls
ALERT
hacker@commands~an-epic-filesystem-quest:/usr/share/jmol/appletweb$ cat ALERT
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/cryptography/hazmat/primitives

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/jmol/appletweb$ cd /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/cryptography/hazmat/primitives
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/cryptography/hazmat/primitives$ ls -a
.             asymmetric         hashes.pyi   padding.pyi
..            ciphers            hmac.pyi     poly1305.pyi
.DISPATCH     cmac.pyi           kdf          serialization
__init__.pyi  constant_time.pyi  keywrap.pyi  twofactor
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/cryptography/hazmat/primitives$ cat .DISPATCH
Tubular find!
The next clue is in: /usr/lib/python3/dist-packages/scipy/linalg/src/id_dist/doc

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/cryptography/hazmat/primitives$ cd /usr/lib/python3/dist-packages/scipy/linalg/src/id_dist/doc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/scipy/linalg/src/id_dist/doc$ ls
NUGGET  doc.tex
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/scipy/linalg/src/id_dist/doc$ cat NUGGET
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/trio/_subprocess_platform/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/scipy/linalg/src/id_dist/doc$ cd /usr/local/lib/python3.8/dist-packages/trio/_subprocess_platform/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/trio/_subprocess_platform/__pycache__$ ls
GIST                     kqueue.cpython-38.pyc  windows.cpython-38.pyc
__init__.cpython-38.pyc  waitid.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/trio/_subprocess_platform/__pycache__$ cat GIST
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{cvjNys6fbctIPP4_Jg2Qx5yL6F3.QX5IDO0wiM1IzNxEzW}

```
Flag: 
pwn.college{cvjNys6fbctIPP4_Jg2Qx5yL6F3.QX5IDO0wiM1IzNxEzW}

### making directories

Solution: used mkdir to make /tmp/pwn, used touch to make file college inside it.

Terminal: 
```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{8_ODzWymYdAuE4UsN-V2oHcGVwI.QXxMDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{8_ODzWymYdAuE4UsN-V2oHcGVwI.QXxMDO0wiM1IzNxEzW}

### finding files

Solution: used find with / as location and flag as the -name parameter. got multiple results, checked each of them. catted the correct file after trial and error

Terminal: 
```bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.eC1BbooKul’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Pagella/Operators/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
hacker@commands~finding-files:~$ cat /usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Pagella/Operators/flag
pwn.college{gHie5goXimIszV_2B_wi0bLZyo5.QXyMDO0wiM1IzNxEzW}
```
Flag: 
pwn.college{gHie5goXimIszV_2B_wi0bLZyo5.QXyMDO0wiM1IzNxEzW}

### linking files

Solution: tried /challenge/catflag. created a symbolic link ~/not-the-flag pointing to /flag. tried /challenge/catflag again. this time it works as now /challenge/catflag reads out ~/not-the-flag which points to /flag.

Terminal: 
```bash
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{4fAM3MKCEMPE2vzziSXeUVWhXhE.QX5ETN1wiM1IzNxEzW}
```
Flag: 
pwn.college{4fAM3MKCEMPE2vzziSXeUVWhXhE.QX5ETN1wiM1IzNxEzW}
