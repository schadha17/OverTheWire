PROBLEM: 
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable

SOLUTION: 

- Execute `find . -size 1033c`. This will output a file
- You can execute `ls -al <filename>` to check if file is a non-executable  
- `file <filename>` will tell you if file is ASCII or text which makes it human-readable 

ALTERNATE SOLUTIONS:

I 

- Execute `find . -size 1033c ! -executable`
- ! refers to not expression (man find)
- '-executable' matches file which are executable by the current user
- However, we would need to manually verify is file is ASCII (human-readable) 

II

- You can simply execute `find . -size 1033c -exec file -- {} \; | grep ASCII`
- 'c' in 1033c refers to bytes (check man find)
- '-exec' and '\;' are used because '-exec <command>' is used to run the <command> such that all following arguments to find are taken as arguments to <command> until ';' is encountered. ';' needs to be escaped with \ char so that shell you run find inside does not treat ';' as its own special character (this special character is used for separating different commands)
- {} is replaced by current file name being processed 
