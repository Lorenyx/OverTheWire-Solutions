# Bandit Level 14 → Level 15
## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Commands you may need to solve this level
- ssh, telnet, nc, openssl, s_client, nmap

## Solution
```
bandit14@bandit:~$ nc localhost 30000
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```
