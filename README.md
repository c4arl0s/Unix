# BashCheatSheet

1. [soft link](https://github.com/c4arl0s/BashCheatSheet#1-soft-link)
2. [find](https://github.com/c4arl0s/BashCheatSheet#2-find)
3. [Shorcuts to quickly move the cursor around the current line](https://github.com/c4arl0s/BashCheatSheet#3-shorcuts-to-quickly-move-the-cursor-around-the-current-line)
4. [tr: The tr utility copies the standard input to the standard output with substitution or deletion of selected characters.](https://github.com/c4arl0s/BashCheatSheet#4-tr-the-tr-utility-copies-the-standard-input-to-the-standard-output-with-substitution-or-deletion-of-selected-characters)
5. [The Difference Between Soft and Hard Links](https://github.com/c4arl0s/BashCheatSheet#5-the-difference-between-soft-and-hard-links)
6. [Symbolic (soft) links](https://github.com/c4arl0s/BashCheatSheet#6-symbolic-soft-links)
7. [Save your scripts on...]()
8. [For Loop with C-style syntax]()
9. [Using For Loop to List Iterate Over Numbers]()
10. [Array Iteration]()
11. [How to use sed to replace strings in macos]()


# 1. [soft link](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

``` bash
ln -s /pathDirectorySource /PathDirectoryWhereYouWantTheLink
```

# 2. [find](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

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

# Hard links

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

# 7. [Save your scripts on...]()

Create a bin directory on your home directory

```console
mkdir bin
```

<img width="924" alt="Screen Shot 2022-09-01 at 12 26 05 a m" src="https://user-images.githubusercontent.com/24994818/187838046-cc5a23cd-8d17-4a93-bca7-815da54251ea.png">

# 8. [For Loop with C-style syntax]()

```bash
for (( i = 0; i < 10; i++ )); do echo "The iteration number is $i"; done
```

```console
The iteration number is 0
The iteration number is 1
The iteration number is 2
The iteration number is 3
The iteration number is 4
The iteration number is 5
The iteration number is 6
The iteration number is 7
The iteration number is 8
The iteration number is 9
```

# 9. [Using For Loop to List Iterate Over Numbers]()

```bash
for i in {1..10}; do echo $i; done
```

```console
1
2
3
4
5
6
7
8
9
10
```

# 10. [Array Iteration]()

```bash
a=(1 2 3 4)
```

```bash
for y in "${a[@]}"; do echo "$y"; done
```

```console
1
2
3
4
```

# 11. How to use sed to replace strings in macos

```console
sed -e "s/,/./" -i '' file.txt
```


