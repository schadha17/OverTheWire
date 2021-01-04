PROBLEM: 

The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size

SOLUTION: 
After successful ssh login using password for level 6, execute: `find . -size 33c -user "bandit7" -group "bandit6"`

Result will be something like: 

```
find: ‘./var/spool/rsyslog’: Permission denied
find: ‘./var/tmp’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/polkit-1’: Permission denied
./var/lib/dpkg/info/bandit7.password
find: ‘./var/log’: Permission denied
find: ‘./var/cache/apt/archives/partial’: Permission denied
```

`cat ./var/lib/dpkg/info/bandit7.password` gets you the key for next level 

