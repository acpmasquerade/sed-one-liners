# Find patterns in the input

- __Find words and group them inside parenthesis__  

````
$ cat input.txt | sed 's/[A-Za-z]*/(&)/g'  
(The) (quick) (brown) (fox) (jumps) (over) (the) (lazy) (dog)
````

