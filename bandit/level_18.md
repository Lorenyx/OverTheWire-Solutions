# Bandit Level 18 → Level 19
## Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## Commands you may need to solve this level
- ssh, ls, cat
```
bandit12@bandit:~$ ssh bandit18@localhost "sh"
bandit18@localhost's password: 
> whoami
bandit18
> cat readme
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```
