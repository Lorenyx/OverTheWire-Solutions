## Bandit Level 2 → Level 3

# Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory

# Commands you may need to solve this level
ls, cd, cat, file, du, find
# Solution
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename" 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
bandit2@bandit:~$
```
