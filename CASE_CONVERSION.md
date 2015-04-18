# Some case conversion examples using sed

## Convert all characters to lowercase
	sed 's/\(.*\)/\L\1/g' some-file.txt

