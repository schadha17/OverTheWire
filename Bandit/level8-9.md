PROBLEM: 

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

SOLUTION: 

We can use a utility called 'uniq'. This command helps us report or omit repeated lines 

`man uniq` suggests us to use `uniq -u input` to only print unique lines

Let's run `uniq -u data.txt`

Oh no! we see a bunch of lines

'uniq' does not detect repeated lines unless they are adjacent. Lets sort the file first so repeated lines are adjacent (`sort data.txt`)

Now, we need to redirect output from `sort data.txt` to input of `uniq -u`. This is where '|' comes into play 

`sort data.txt | uniq -u` gets you the answer

