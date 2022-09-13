# sed-one-liners

## Basic understanding
- `sed 's/<match-pattern>/<replace-pattern>/g' <some-filename.txt>`
- to replace infile `sed -i 's/<....`

## Switches
- /g (global)
- /p (print)
- /I (ignore case)
- /w some-filename (write to some-filename)

## Substitute command 's/...'
- /../../	  Delimiter
- match-pattern	  Regular Expression Pattern Search Pattern
- replacement-pattern	  Replacement string

## Transliterate command 'y/...'
- y/source/dest/
- Transliterate the characters in the pattern space which appear in source to the corresponding character in dest.
- one to one mapping
- Example : `'y/0123/_abc/'` replaces the stream as 
  - 0 -> _
  - 1 -> a
  - 2 -> b
  - 3 -> c

## Delimiters
__/ is not the only delimiter. Use # or _ or anything convinient__

## Chain and pipe expressions
`sed -e 'first-expression' -e 'second-expression' ...`
`cat some-file-input | sed 'some-expression'`

# REFERENCES
http://www.grymoire.com/Unix/Sed.html#uh-1


# Commands

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



