# Bandit Level 12 → Level 13
## Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.
For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Commands you may need to solve this level
- grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

## Solution
```
bandit12@bandit:~$ mktemp -d
/tmp/tmp.F0Ri82ps6S
bandit12@bandit:~$ cd /tmp/tmp.F0Ri82ps6S
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ cp ~/data.txt .
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ xxd -r data.txt > file1
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file file1 
file1: gzip compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ mv file1 file1.gz
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ gzip -d file1.gz 
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ tar -xf file1
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data5.bin  data.txt  file1  file2
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data5.bin  data6.bin  data.txt  file1  file2
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ bzip2 -df data6.bin > file3
bzip2: Can't guess original name for data6.bin -- using data6.bin.out
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data6.bin.out 
data6.bin.out: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ tar -df data6.bin.out
tar: data8.bin: Warning: Cannot stat: No such file or directory
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data8.bin
data8.bin: cannot open `data8.bin' (No such file or directory)
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data5.bin  data6.bin.out  data.txt  file1  file2  file3
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ tar -xf data6.bin.out
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data5.bin  data6.bin.out  data8.bin  data.txt  file1  file2  file3
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ mv data8.bin data.gz
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ gzip -d data.gz
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ ls
data  data5.bin  data6.bin.out  data.txt  file1  file2  file3
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ file data
data: ASCII text
bandit12@bandit:/tmp/tmp.F0Ri82ps6S$ cat data
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
