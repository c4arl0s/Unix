# BashCheatSheet

1. [soft link](https://github.com/c4arl0s/BashCheatSheet#1-soft-link)
2. [Shorcuts to quickly move the cursor around the current line](https://github.com/c4arl0s/BashCheatSheet#3-shorcuts-to-quickly-move-the-cursor-around-the-current-line)
3. [The Difference Between Soft and Hard Links](https://github.com/c4arl0s/BashCheatSheet#5-the-difference-between-soft-and-hard-links)
4. [Symbolic (soft) links](https://github.com/c4arl0s/BashCheatSheet#6-symbolic-soft-links)
5. [Save your scripts on...]()
6. [How to use sed to replace strings in macos]()
7. [Create an hyperlink command line]()


# 1. [soft link](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

``` bash
ln -s /pathDirectorySource /PathDirectoryWhereYouWantTheLink
```

# 2. [Shorcuts to quickly move the cursor around the current line](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

Enable Meta key. Open Terminal > Preferences > Settings > Keyboard, and enable Use Option as meta key.

- ctrl-A: Go to beginning of the line.
- ctrl-E:	Go to the end of the line.

enable Metadata Key, then you can use:

- alt-f: Go forward one word
- alt-b: Go backwards one word	-> Very useful

# 3. [The Difference Between Soft and Hard Links](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

# Hard links

- Only link to a file not a directory
- Can not reference a file on a different disk/volume
- Links will reference a file even if it is moved
- Links reference inode/physical locations on the disk

# 4. [Symbolic (soft) links](https://github.com/c4arl0s/BashCheatSheet#bashcheatsheet)

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

# 5. [Save your scripts on...]()

Create a bin directory on your home directory

```console
mkdir bin
```

<img width="924" alt="Screen Shot 2022-09-01 at 12 26 05 a m" src="https://user-images.githubusercontent.com/24994818/187838046-cc5a23cd-8d17-4a93-bca7-815da54251ea.png">

# 12. Create an hyperlink command line

Using `echo`

```bash
echo -e '\e]8;;http://example.com\aThis is a hyperlink\e]8;;\a' 
```

Using printf


```bash
printf '\e]8;;http://example.com\e\\This is a link\e]8;;\e\\\n'
```

# Redirect Output and Errors to `/dev/null`

The following files are used by Unix process.

```console
ls -l /dev/{stdout,stdin,stderr}
```

COnsole output:

```console
lr-xr-xr-x  1 root  wheel  0 Nov 26 16:33 /dev/stdout -> fd/1
lr-xr-xr-x  1 root  wheel  0 Nov 26 16:33 /dev/stdin -> fd/0
lr-xr-xr-x  1 root  wheel  0 Nov 26 16:33 /dev/stderr -> fd/2
```

1. `/dev/stdin` ( 0 ) – Standard Input (usually keyboard or file). When a command opens `/dev/stdin`, it can read input from the user.
2. `/dev/stdout` ( 1 ) – Standard Output (usually screen). When a command writes to `/dev/stdout`, its output is displayed on the screen.
3. `/dev/stderr` ( 2 ) – Standard Error (usually screen). When a program or command writes to `/dev/stderr`, its error messages are displayed on the screen.

# What is a `/dev/null` file in Unix?

`/dev/null` discards data in Unix systems. Used to suppress program output.

```console
command1 >/dev/null         # redirects standard output to /dev/null
```

```console
command1 >/dev/null 2>&1    # redirects standard output to /dev/null, 2>&1 operator redirects standard error to the same location as standard output. 
```
