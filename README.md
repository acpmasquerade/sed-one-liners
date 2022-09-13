# sed-one-liners

## Case Conversion

__Convert all characters to lowercase__
````
sed 's/\(.*\)/\L\1/g' some-file.txt
````

__Convert all characters to uppercase__
````
sed 's/\(.*\)/\U\1/g' some-file.txt
````

__Capitalize first word, making everything lowercase__
````
sed 's/\(.\)\(.*\)/\U\1\L\2/g' some-file.txt
````

__Capitalize first letter of each word__
````
sed 's/\b\(.\)/\U\1/g' some-file.txt
````

## Find patterns in the input
__Find words and group them inside parenthesis__  
````
$ cat input.txt | sed 's/[A-Za-z]*/(&)/g'  
(The) (quick) (brown) (fox) (jumps) (over) (the) (lazy) (dog)
````



