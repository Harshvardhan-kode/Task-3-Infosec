## Challenge: Bandit Level 5 → Level 6

Hiding secrets via obscure filenames is ineffective; attackers enumerate systematically using file metadata.

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

Misconfigured permissions expand the attack surface, exposing secrets even outside user home directories.

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

Storing secrets in plaintext relies on obscurity and fails against simple content inspection.

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

Redundancy does not provide security; basic data filtering easily isolates anomalies.

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

Encoding data inside files does not secure it; inspection tools reveal embedded secrets

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

Encoding is reversible and should never be treated as encryption.

**Commands Used:**
```bash
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
**passord for next level:**
```bash
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
