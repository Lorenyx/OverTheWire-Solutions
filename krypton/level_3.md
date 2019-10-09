# Krypton Level 3 → Level 4
## Level Info
Well done. You’ve moved past an easy substitution cipher.

The main weakness of a simple substitution cipher is repeated use of a simple key. In the previous exercise you were able to introduce arbitrary plaintext to expose the key. In this example, the cipher mechanism is not available to you, the attacker.

However, you have been lucky. You have intercepted more than one message. The password to the next level is found in the file ‘krypton4’. You have also found 3 other files. (found1, found2, found3)

You know the following important details:

The message plaintexts are in English (*** very important) - They were produced from the same key (*** even better!)
Enjoy.

## Solution
```
krypton3@krypton:/krypton/krypton3$ cd /krypton/krypton3/
krypton3@krypton:/krypton/krypton3$ cat krypton4 | tr "[:upper:]" "[:lower:]" | tr "qazwsxedcrfvtgbyhnujmikolp" "a-z"
welld oneth eleve lfour passw ordis brute
```
## Notes
- I used the an online tool to find the key using subtitution and frequency analysis. https://www.guballa.de/substitution-solver
- The password should also be in UPPERCASE. Because the key was given in lowercase I converted the text to lowercase.
