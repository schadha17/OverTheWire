
This is the password you need for establishing an ssh session for bandit1 username: boJ9jbbUNNfktd78OOpsqOltutMc3MY1 (you can get this by solving Level 0 -> Level 1) 

You establish a session using `ssh bandit1@bandit.labs.overthewire.org -p 2220` (username@hostname -p [PORT NUMBER])

After a successful login, you will find that home directory has a file named "-". The password is stored in this file. 

Lets open it: `vi -` or `cat -` 

stdin? :( 

What's happening is `cat -` echoes stdin, in this case keyboarded user input, to stdout. It is not able to recognize "-" as a file. 

`cat ./-` would do the job for you ;) 

 
