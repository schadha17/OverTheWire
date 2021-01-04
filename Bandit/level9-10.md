LEVEL GOAL: 

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

SOLN: 

- Let's grep for '=' character using `grep = data.txt`

- It gives us, Binary file data.txt matches

- In other words, data.txt is a binary file and we cannot grep on it. We can do `grep -a = data.txt` which processes the binary file as it were text but this does not seem to work as well 

- Let us use strings command now. GNU strings prints the printable character sequences that are at least 4 characters long

- Let's execute `string data.txt`

- You will see a bunch of strings from the file

- Now, we can simply search for ='s using `string data.txt | grep =`

- A faster and more elegant solution would be to use `strings data.txt | grep -E "==+" data.txt`. 

- grep -E allows us to search using regular expressions

```
       The preceding item is optional and matched at most once.
       *      The preceding item will be matched zero or more times.
       +      The preceding item will be matched one or more times.
       {n}    The preceding item is matched exactly n times.
       {n,}   The preceding item is matched n or more times.
       {,m}   The preceding item is matched at most m times.  This is a GNU extension.
       {n,m}  The preceding item is matched at least n times, but not more than m times.
```
