# Narnia Level 3 → Level 4

## Solution
```
leviathan3@leviathan:~$ ltrace ./level3
__libc_start_main(0x8048618, 1, 0xffffd794, 0x80486d0 <unfinished ...>
strcmp("h0no33", "kakaka")                                                                   = -1
printf("Enter the password> ")                                                               = 20
fgets(Enter the password> pass
"pass\n", 256, 0xf7fc55a0)                                                             = 0xffffd5a0
strcmp("pass\n", "snlprintf\n")                                                              = -1
puts("bzzzzzzzzap. WRONG"bzzzzzzzzap. WRONG
)                                                                   = 19
+++ exited (status 0) +++
leviathan3@leviathan:~$ ./level3 
Enter the password> snlprintf
[You've got shell]!
$ whoami
leviathan4
$ cat /etc/leviathan_pass/leviathan4
vuH0coox6m
```
