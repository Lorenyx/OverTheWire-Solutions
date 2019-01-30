# Leviathan Level 4 → Level 5

## Solution
```
leviathan4@leviathan:~$ ls
leviathan4@leviathan:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile  .trash
leviathan4@leviathan:~$ cd .trash
leviathan4@leviathan:~/.trash$ ls
bin
leviathan4@leviathan:~/.trash$ ./bin 
01010100 01101001 01110100 01101000 00110100 01100011 01101111 01101011 01100101 01101001 00001010 
leviathan4@leviathan:~/.trash$ python
Python 2.7.13 (default, Sep 26 2018, 18:42:22) 
[GCC 6.3.0 20170516] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import binascii
>>> n = int("0b0101010001101001011101000110100000110100011000110110111101101011011001010110100100001010", 2)
>>> binascii.unhexlify("%x" % n)
'Tith4cokei\n'
>>> 
```
