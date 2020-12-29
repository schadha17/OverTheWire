PROBLEM: 
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable

SOLUTION: 

- Execute `find . -size 1033c`. This will output a file
- You can execute `ls -al <filename>` to check if file is a non-executable  
- `file <filename>` will tell you if file is ASCII or text which makes it human-readable 
