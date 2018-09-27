# Krypton Level 0 → Level 1
## Level Info
The password for level 2 is in the file ‘krypton2’. It is ‘encrypted’ using a simple rotation. It is also in non-standard ciphertext format. When using alpha characters for cipher text it is normal to group the letters into 5 letter clusters, regardless of word boundaries. This helps obfuscate any patterns. This file has kept the plain text word boundaries and carried them to the cipher text. Enjoy!

## Solution
```
krypton1@krypton:/krypton/krypton1$ cat krypton2 
YRIRY GJB CNFFJBEQ EBGGRA
krypton1@krypton:/krypton/krypton1$ cat krypton2 | tr 'N-ZA-M' 'A-Z'
LEVEL TWO PASSWORD ROTTEN
```
