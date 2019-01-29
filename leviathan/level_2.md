# Leviathan Level 1 → Level 2

## Solution 
```
leviathan1@leviathan:~$ ls
check
leviathan1@leviathan:~$ ./check 
password: rioGegei8m
Wrong password, Good Bye ...
leviathan1@leviathan:~$ ltrace ./check 
__libc_start_main(0x804853b, 1, 0xffffd794, 0x8048610 <unfinished ...>
printf("password: ")                                                                         = 10
getchar(1, 0, 0x65766f6c, 0x646f6700password: pass
)                                                        = 112
getchar(1, 0, 0x65766f6c, 0x646f6700)                                                        = 97
getchar(1, 0, 0x65766f6c, 0x646f6700)                                                        = 115
strcmp("pas", "sex")                                                                         = -1
puts("Wrong password, Good Bye ..."Wrong password, Good Bye ...
)                                                         = 29
+++ exited (status 0) +++
leviathan1@leviathan:~$ ./check 
password: sex
$ whoami
leviathan2
$ cat /etc/leviathan_pass/leviathn2
cat: /etc/leviathan_pass/leviathn2: No such file or directory
$ cat /etc/leviathan_pass/leviathan2
ougahZi8Ta
```
