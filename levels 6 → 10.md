## Challenge: Bandit Level 5 → Level 6

Simply hiding files deeper or naming them oddly does not protect sensitive data.

**Commands Used:**
```bash
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ file ./maybehere07/.file2
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
```
**passord for next level:**
```bash
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

## Challenge: Bandit Level 6 → Level 7

Poor permission management can expose secrets anywhere on the system.

**Commands Used:**
```bash
bandit5@bandit:~$ cd inhere
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/ba
bandit7.password           base-files.prerm           base-passwd.templates      bash.conffiles
base-files.conffiles       base-files.triggers        bash-completion.conffiles  bash.list
base-files.list            base-passwd.list           bash-completion.list       bash.md5sums
base-files.md5sums         base-passwd.md5sums        bash-completion.md5sums    bash.postinst
base-files.postinst        base-passwd.postinst       bash-completion.postinst   bash.postrm
base-files.postrm          base-passwd.postrm         bash-completion.postrm     bash.prerm
base-files.preinst         base-passwd.preinst        bash-completion.preinst
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
```
**passord for next level:**
```bash
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

## Challenge: Bandit Level 7 → Level 8

Storing passwords in plain text makes them easy to discover.

**Commands Used:**
```bash
bandit7@bandit:~$ grep millionth data.txt
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
**passord for next level:**
```bash
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

## Challenge: Bandit Level 8 → Level 9

Repetition does not add security; simple filtering reveals sensitive data.

**Commands Used:**
```bash
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
**passord for next level:**
```bash
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

## Challenge: Bandit Level 9 → Level 10

Hiding data in unusual file formats does not prevent access.

**Commands Used:**
```bash
bandit9@bandit:~$ strings data.txt | grep "==="
========== the
========== password
E========== is
5========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
**passord for next level:**
```bash
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## Challenge: Bandit Level 10 → Level 11

Encoding is not encryption and offers no real security.

**Commands Used:**
```bash
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
**passord for next level:**
```bash
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
