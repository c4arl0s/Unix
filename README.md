# BashCheatSheet
BashCheatSheet

1. [soft link](https://github.com/c4arl0s/BashCheatSheet#1-soft-link)
2. [find](https://github.com/c4arl0s/BashCheatSheet#2-find)
3. [Shorcuts to quickly move the cursor around the current line](https://github.com/c4arl0s/BashCheatSheet#3-shorcuts-to-quickly-move-the-cursor-around-the-current-line)
4. [tr: The tr utility copies the standard input to the standard output with substitution or deletion of selected characters.](https://github.com/c4arl0s/BashCheatSheet#4-tr-the-tr-utility-copies-the-standard-input-to-the-standard-output-with-substitution-or-deletion-of-selected-characters)
5. [The Difference Between Soft and Hard Links](https://github.com/c4arl0s/BashCheatSheet#5-the-difference-between-soft-and-hard-links)
6. [Symbolic (soft) links](https://github.com/c4arl0s/BashCheatSheet#6-symbolic-soft-links)



# 1. [soft link](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

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

# 3. [Shorcuts to quickly move the cursor around the current line](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

Enable Meta key. Open Terminal > Preferences > Settings > Keyboard, and enable Use Option as meta key.

- ctrl-A: Go to beginning of the line.
- ctrl-E:	Go to the end of the line.

enable Metadata Key, then you can use:

- alt-f: Go forward one word
- alt-b: Go backwards one word	-> Very useful

# 4. [tr: The tr utility copies the standard input to the standard output with substitution or deletion of selected characters.](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

substitute white space to -  

``` bash
tr ' ' '-'
```

# 5. [The Difference Between Soft and Hard Links](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

## Hard links

- Only link to a file not a directory
- Can not reference a file on a different disk/volume
- Links will reference a file even if it is moved
- Links reference inode/physical locations on the disk

# 6. [Symbolic (soft) links](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

- Can link to directories
- Can reference a file/folder on a different hard disk/volume
- Links remain if the original file is deleted
- Links will NOT reference the file anymore if it is moved
- Links reference abstract filenames/directories and NOT physical locations. They are given their own inode

Example 1:
```bash
$ ln -s /Users/carlossantiagocruz/Documents/BASH-PROGRAMMING/DICT-EN-ES/trad3.sh /usr/local/bin/trad3
```
Example 2:
```bash
ln -s /Users/carlossantiagocruz/Documents/BASH-PROGRAMMING/MOVER-PDF-2-DIRECTORIO/mover-pdf2directorio.sh /usr/local/bin/mover-pdf2directorio1.0
```

