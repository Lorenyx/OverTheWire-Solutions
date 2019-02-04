# Bandit Level 16 → Level 17
## Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the 
range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL 
and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you 
send to it.

## Commands you may need to solve this level
- ssh, telnet, nc, openssl, s_client, nmap

## Solution
```
bandit16@bandit:~$ nmap localhost -p31000-32000

Starting Nmap 7.40 ( https://nmap.org ) 
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00019s latency).
Not shown: 999 closed ports
PORT      STATE SERVICE
31518/tcp open  unknown
31790/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790 

cluFn7wTiGryunymYOu4RcffSxQluehd
Correct!
-----BEGIN RSA PRIVATE KEY-----
<..RSA Key..>
-----END RSA PRIVATE KEY-----


bandit16@bandit:~$ mktemp -d
/tmp/tmp.OhfDOkqaZj
bandit16@bandit:~$ cd /tmp/tmp.OhfDOkqaZj
bandit16@bandit:/tmp/tmp.OhfDOkqaZj$ touch secret.key
bandit16@bandit:/tmp/tmp.OhfDOkqaZj$ chmod 700 secret.key 
bandit16@bandit:/tmp/tmp.OhfDOkqaZj$ nano secret.key 
< paste key into file >
bandit16@bandit:/tmp/tmp.OhfDOkqaZj$ ssh bandit17@localhost -i secret.key 

bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn
```
