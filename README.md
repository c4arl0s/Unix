# BashCheatSheet
BashCheatSheet

# soft link

``` bash
ln -s /pathDirectorySource /PathDirectoryWhereYouWantTheLink
```

# find

``` bash
find . -type f -name "*Old*.ppt"
```

- .       it means that you want to look into the current directory.
- -type   it means the type of file you want to find
- f       it me:ans file type
- -name   it means that you want to find by name
- ""      you have to put "" characteres it you want to use special characters to find an specific file.

``` bash
find . -type f -name "*Old*.ppt"
find . -name *NORMA* -type d
find . -name "*" -type f
```

# Shorcuts to quickly move the cursor around the current line

Enable Meta key. Open Terminal > Preferences > Settings > Keyboard, and enable Use Option as meta key.

- ctrl-A: Go to beginning of the line.
- ctrl-E:	Go to the end of the line.

enable Metadata Key, then you can use:
alt-f: Go forward one word
alt-b: Go backwards one word	-> Very useful

# tr: The tr utility copies the standard input to the standard output with substitution or deletion of selected characters.

substitute white space to -  

``` bash
tr ' ' '-'
```


