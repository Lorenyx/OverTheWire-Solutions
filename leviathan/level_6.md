# Leviathan Level 6 → Level 7

## Solution
```
leviathan6@leviathan:~$ ls
leviathan6
leviathan6@leviathan:~$ mktemp -d
/tmp/tmp.DG8YfxFHvE
leviathan6@leviathan:~$ /tmp/tmp.DG8YfxFHvE
-bash: /tmp/tmp.DG8YfxFHvE: Is a directory
leviathan6@leviathan:~$ cd /tmp/tmp.DG8YfxFHvE
leviathan6@leviathan:/tmp/tmp.DG8YfxFHvE$ touch bruteforce.sh
leviathan6@leviathan:/tmp/tmp.DG8YfxFHvE$ nano bruteforce.sh 
leviathan6@leviathan:/tmp/tmp.DG8YfxFHvE$ chmod u+x bruteforce.sh 
leviathan6@leviathan:/tmp/tmp.DG8YfxFHvE$ ./bruteforce.sh 
```

## bruteforce.sh
```
#!/bin/bash

for n in {0000..9999}; do
~/leviathan6 $n
done
```
