PROBLEM: 

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

SOLUTION: 

After you ssh in, you will see a bunch of files -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09

We need to find a file out of these which is human readable

Execute `file --mime-type -- *` (-- means whatever is passed as a parameter, treat it as a string instead of parameters for the command) 

```
-file00: application/octet-stream
-file01: application/octet-stream
-file02: application/octet-stream
-file03: application/octet-stream
-file04: application/octet-stream
-file05: application/octet-stream
-file06: application/octet-stream
-file07: text/plain
-file08: application/octet-stream
-file09: application/octet-stream
```

You can also execute `file -- *` and this will give you the following output 

```
-file00: data
-file01: data
-file02: data
-file03: data
-file04: data
-file05: data
-file06: data
-file07: ASCII text
-file08: data
-file09: data
```

Quite evident that we need to open -file07. Try running `cat -file07`. We get an error 

cat: invalid option -- 'f'

Notice why `cat -- -file07` fixes the above described issue. 


