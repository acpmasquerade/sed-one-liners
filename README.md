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

#REFERENCES
http://www.grymoire.com/Unix/Sed.html#uh-1

-------------------
# Commands
-------------------

- Convert all characters to lowercase
`sed 's/\(.*\)/\L\1/g' some-file.txt`
- Convert all characters to uppercase
`sed 's/\(.*\)/\U\1/g' some-file.txt`
- Capitalize first word, making everything lowercase
`sed 's/\(.\)\(.*\)/\U\1\L\2/g' some-file.txt`
- Capitalize first letter of each word
`sed 's/\b\(.\)/\U\1/g' some-file.txt`
