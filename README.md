# BashCheatSheet
BashCheatSheet

``` bash
while [ 1 ]; do echo "repitiendo"; sleep 1; done | pv > /dev/null
```

``` bash
Note: Hold option (alt) and click a position in the current line to move your cursor to that position.

Clear history: ctrl + l

Clear everything left from current cursor position: ctrl + u

Clear everything right from current cursor position: ctrl + k

Re-call last input with sudo: sudo !!

Stop current process: ctrl + c

Jump to left: ctrl + a

Jump to right: ctrl + e

Help: help cd / help dir (...)

Finding Help: apropos directory / apropos search (...)

Define custom startup screen: sudo nano /etc/motd

Run a script as background process: python script.py &

List all running process's: ps aux

Kill a running process: sudo kill 12345

System

Get the current path: pwd

Copy to clipboard: pwd | pbcopy

Paste: pbpaste

Get the current hostname: hostname

Get the current users: users

Get all info about the environment: env

Show calendar: cal

Show today's date: date

Exit terminal: exit

Permissions

Use -R option to change permissions recursively.

List: ps -ef | grep apache | grep -v grep

Change permissions: chmod 755 index.php

Change owner: chown root index.php (root is the username)

Change group: chgrp www-data index.php (www-data is the groupname)

WordPress Files/Folder Permissions

Let apache be owner: chown www-data:www-data -R *

Change directory permissions rwxr-xr-x: find . -type d -exec chmod 755 {} \;

Change file permissions rw-r--r--: find . -type f -exec chmod 644 {} \;

(see http://stackoverflow.com/a/18352747/1815847)

Directories

List directory contents: ls

List all directory contents sorted by time edited: ls -alt

List directory (wildcard matching): ls *.txt

List all files of type: find . -name "*.txt" -print

Go back to previous directory: cd -

Make (empty) directory: mkdir sample-dirname

Remove (empty) directory: rmdir sample-dirname

Remove directory with all contents: rm -rf sample-dirname/

Remove directory contents and keep directory: rm -rf *

Checkout directory: cd sample-dirname

Browsing directories: pushd sample-dirname / popd / dirs (see http://unix.stackexchange.com/a/77081)

Symlinks

Create symlink: ln -s source-dirname destination-dirname

Update symlink: ln -sfn source-dirname destination-dirname

Remove symlink: unlink sample-dirname

-s: Create a symbolic link.
-f: If the target file already exists, then unlink it.
-F: If the target file already exists and is a directory, then remove/overwrite it.
-h: If the target file or directory is a symbolic link, do not follow it.
-n: Same as -h, for compatibility with other ln implementations.
Files

Make (empty) file: touch sample-filename.txt

Change creation date: touch –t 201401011337 sample-filename.txt

Change modified date: touch –mt 201401011337 sample-filename.txt

Duplicate file: cp sample-filename.txt sample-filename-copy.txt

Copy/Page folder with content: cp -a folder/ new_folder

Move/Rename file: mv current-filename.txt new-filename.txt

Move/Rename file and prompt before overwriting an existing file: mv -i current-filename.txt new-filename.txt

Remove file: rm sample-filename.txt

View file: less sample-filename.txt / more sample-filename.txt

Write to file (will overwrite existing content): cat > sample-filename.txt (quit with ctrl+d)

Search for a filename (not content!) in the current directory: find sample-filename.txt

Search for a string (not filename!) inside all files in the current directory: ack "string" --php (documentation)

Search for a string inside all files in the current directory and subdrectories: grep -r "string" *

Search and replace within file: sed -i '' 's/original-text/new-text/g' sample-filename.txt

MD5 hash for files: md5 sample-filename.txt

MD5 hash for folders: tar c folder | md5sum

Encrypt file: openssl enc -aes-256-cbc -e -in sample-filename.txt -out sample-encrypted.txt

Decrypt file: openssl enc -aes-256-cbc -d -in sample-encrypted.txt -out sample-filename.txt

Server

Access via ssh: ssh pi@192.168.0.0

Copy file from server to local: scp pi@192.168.0.0:/path/to/file.png ~/Desktop/ (use -r to recursively get complete folder)

Copy file from local to server: scp ~/Desktop/file.png pi@192.168.0.0:/path/to/folder (use -r to recursively get complete folder)

Escape files with spaces in name like this: /path/to/file\\\ name.png

Apps

Start appliction: open -a [name-of-programm] e.g. open -a firefox

Open finder with current folder: open .

Variables

Register variable: export TESTING="Sample Text"

Echo variable: echo $TESTING

Unset variable: unset TESTING

Output & Redirects

Write to file: echo "Hello" > hello.txt

Append content from a file to another file: cat file1.txt >> file2.txt

Add the amount of lines, words, and characters to file2.txt: cat file1.txt | wc | cat > file2.txt

Sort the content of a file (like cat): sort hello.txt

Save to sorted content to a new file: cat file1.txt | sort > sorted-file1.txt

Sort and remove duplicates and save to a new file: sort file1.txt | uniq > uniq-file1.txt

Functions

Calculate (returns only int): echo $((123/2))

Web

Check site feedback: ping google.com

Show site IP: dig +short google.com

Show A Record: dig a google.com (Returns: google.com. 43 IN A 123.123.123.123 aka public-name ttl internet record-type server-address)

Webservice: https://www.whatsmydns.net/

Curl headers: curl -I https://hofmannsven.com

Tools

Tree

Installation: brew install tree

HTTPie

Installation: brew install httpie

Usage:

http GET https://hofmannsven.test --verify=no
Security

Fix OpenSSH Client Bug: https://www.digitalocean.com/community/questions/openssh-client-bug-cve-2016-0777-and-cve-2016-0778
Raw
 nano.md
Nano CLI Basics

Jump to end of file: ctrl + w + v```
``` bash
If you have a pdf with scanned images, you can use convert to create a pdf with jpeg compression (You can use this method on any pdf, but you'll loose all text informations).

For example:
convert -density 200x200 -quality 60 -compress jpeg input.pdf output.pdf```
``` bash
Cursor movement VIM
h - move cursor left
j - move cursor down
k - move cursor up
l - move cursor right
H - move to top of screen
M - move to middle of screen
L - move to bottom of screen
w - jump forwards to the start of a word
W - jump forwards to the start of a word (words can contain punctuation)
e - jump forwards to the end of a word
E - jump forwards to the end of a word (words can contain punctuation)
b - jump backwards to the start of a word
B - jump backwards to the start of a word (words can contain punctuation)
% - move to matching character (default supported pairs: '()', '{}', '[]' - use :h matchpairs in vim for more info)
0 - jump to the start of the line
^ - jump to the first non-blank character of the line
$ - jump to the end of the line
g_ - jump to the last non-blank character of the line
gg - go to the first line of the document
G - go to the last line of the document
5G - go to line 5
fx - jump to next occurrence of character x
tx - jump to before next occurrence of character x
Fx - jump to previous occurence of character x
Tx - jump to after previous occurence of character x
; - repeat previous f, t, F or T movement
, - repeat previous f, t, F or T movement, backwards
} - jump to next paragraph (or function/block, when editing code)
{ - jump to previous paragraph (or function/block, when editing code)
zz - center cursor on screen
Ctrl + e - move screen down one line (without moving cursor)
Ctrl + y - move screen up one line (without moving cursor)
Ctrl + b - move back one full screen
Ctrl + f - move forward one full screen
Ctrl + d - move forward 1/2 a screen
Ctrl + u - move back 1/2 a screen
Tip Prefix a cursor movement command with a number to repeat it. For example, 4j moves down 4 lines.```
``` bash
yy - yank (copy) a line
2yy - yank (copy) 2 lines
yw - yank (copy) the characters of the word from the cursor position to the start of the next word
y$ - yank (copy) to end of line
p - put (paste) the clipboard after cursor
P - put (paste) before cursor
dd - delete (cut) a line
2dd - delete (cut) 2 lines
dw - delete (cut) the characters of the word from the cursor position to the start of the next word
D - delete (cut) to the end of the line
d$ - delete (cut) to the end of the line
x - delete (cut) character
```
``` bash

/Applications/LibreOffice.app/Contents/MacOS/soffice --headless --convert-to pdf $archivos_doc
```
``` bash
Cut and Paste

yy - yank (copy) a line
2yy - yank 2 lines
yw - yank word
y$ - yank to end of line
p - put (paste) the clipboard after cursor
P - put (paste) before cursor
dd - delete (cut) a line
dw - delete (cut) the current word
x - delete (cut) current character
```
``` bash
youtube-dl https://www.facebook.com/neurojk/videos/1465798600177247/

teclear youtube-dl, seguido de la dirección url del video.```
``` bash
how to remove white spaces bash

Some Linux tools does not properly work with files which include spaces in their names. This simple
bash for loop (/bash-scripting-tutorial#h12-1-bash-for-loop) will remove white space from file names
and rename/move for all files in the given directory.

First enter directory with cd:

cd /my/directory

and then run:

Remueve espacios en blanco con guiones:

for f in *; do mv "$f" `echo $f | tr ' ' '-'`; done

remueve espacios en blanco con guiones bajos:

for f in *; do mv "$f" `echo $f | tr '_' '_'`; done
```
``` bash
Renombrar todos los archivos de mayusculas a minúsculas:

for i in `find . -name "*" -type f | grep -e "[A-Z]"`; do j=`echo $i | tr '[A-Z]' '[a-z]' | sed s/\-1$//`; mv $i $i-1; mv $i-1 $j; done

Explained

find . -name "*" -type f	: busca todos los archivos de tipo file en el directorio actual.
grep -e "[A-Z]"             : filtra todos los archivos que por lo menos tengan una mayuscula.
sed s/\-1$//                : sed reemplaza 
=================================================================
renombrar los archivos del directorio actual a minusculas (todos)

for FILE in * ; do mv $FILE `echo $FILE | tr '[A-Z]' '[a-z]'` ; done
==================================================================

renombrar los arhicvos del directorio actual de mayusculas a minusculas:

rename -f 'y/A-Z/a-z/' *
====================================================================
renombrar archivos:

find . -type f -print0 | xargs -0n 1 bash -c \ 's=$(dirname "$0")/$(basename "$0"); d=$(dirname "$0")/$(basename "$0"|tr "[A-Z]" "[a-z]"); mv -f "$s" "$d"'
```
``` bash
Basic moves

Move back one character. Ctrl + b
Move forward one character. Ctrl + f
Delete current character. Ctrl + d
Delete previous character. Backspace
Undo. Ctrl + -

Moving faster

Move to the start of line. Ctrl + a
Move to the end of line. Ctrl + e
Move forward a word. Meta + f (a word contains alphabets and digits, no symbols)
Move backward a word. Meta + b
Clear the screen. Ctrl + l

Cut and paste (‘Kill and yank’ for old schoolers)

Cut from cursor to the end of line. Ctrl + k
Cut from cursor to the end of word. Meta + d
Cut from cursor to the start of word. Meta + Backspace
Cut from cursor to previous whitespace. Ctrl + w
Paste the last cut text. Ctrl + y
Loop through and paste previously cut text. Meta + y (use it after Ctrl + y)
Loop through and paste the last argument of previous commands. Meta + .

Search the command history

Search as you type. Ctrl + r and type the search term; Repeat Ctrl + r to loop through results.
Search the last remembered search term. Ctrl + r twice.
End the search at current history entry. Ctrl + j
Cancel the search and restore original line. Ctrl + g
```
``` bash
I have a file with many lines in each line there are many columns(fields) separated by blank " " the numbers of columns in each line are different I want to remove the first two columns how to?

cut -d " " -f 3- input_filename > output_filename
Explanation:

cut: invoke the cut command
-d " ": use a single space as the delimiter (cut uses TAB by default)
-f: specify fields to keep
3-: all the fields starting with field 3
input_filename: use this file as the input
> output_filename: write the output to this file.
Alternatively, you can do it with awk:

awk '{$1=""; $2=""; sub("  ", " "); print}' input_filename > output_filename
Explanation:

awk: invoke the awk command
$1=""; $2="";: set field 1 and 2 to the empty string
sub(...);: clean up the output fields because fields 1 & 2 will still be delimited by " "
print: print the modified line
input_filename > output_filename: same as above.
```
``` bash
find . -type f -name "*Old*.ppt"

.       it means that you want to look into the current directory.
-type   it means the type of file you want to find
f       it me:ans file type
-name   it means that you want to find by name
""      you have to put "" characteres it you want to use special characters to find an specific file.

find . -type f -name "*Old*.ppt"

find . -name *NORMA* -type d

find . -name "*" -type f

Buscar por el contenido del archivo

Si desea buscar archivos basados en el contenido de texto real dentro del archivo puede combinarse el comando Buscar con otros comandos de unix utilizando la -exec indicador.

Por ejemplo, combinando -exec con muy poderosa herramienta grep, puede encontrar todos los denominada foo archivos como antes que también contienen texto concreto:

find . -type f -name "*" -exec grep -i "device is" /dev/null {} +

/root/misc/foobar.sh:My favorite foods are:
/root/misc/foo:My favorite foods are:
/root/other/foobar.txt:My favorite foods are:
El comando completo parece desalentadora, pero realmente sólo consta de dos partes básicas:

find / -type f -name foo*
Que es la funcionalidad básica del comando Buscar cubierto hasta ahora en que este tutorial, aquí estamos buscando todos los archivos de la typefile cuyos nombres empiecen por foo.

-exec grep -i "My favorite foods are" /dev/null {} +
La última mitad del comando utiliza el nuevo -exec indicador, seguido por el comando de unix que desea ejecutar en los resultados de buscar. En este caso es el componente clave:

grep -i "My favorite foods are"
Realiza una búsqueda en el contenido de los archivos (minúsculas debido a la -i indicador) para el texto "Mis comidas favoritas son".

Ahora ejecuta el mismo comando, pero en su lugar buscando "apple" vemos que hay sólo dos archivos que tienen apple aparece como uno de los alimentos favoritos:

find / -type f -name foo* -exec grep -i "apple" /dev/null {} +
/root/misc/foobar.sh:apple
/root/other/foobar.txt:apple
Aunque esto es sólo una breve introducción del uso de -exec de búsqueda grep indicador dentro de su búsqueda, le ofrece un muy alto nivel de versatilidad y potencia en las búsquedas.

```
``` bash
or to zip a directory

zip -r squash.zip dir1
```
``` bash
Insert mode - inserting/appending text

i - insert before the cursor
I - insert at the beginning of the line
a - insert (append) after the cursor
A - insert (append) at the end of the line
o - append (open) a new line below the current line
O - append (open) a new line above the current line
ea - insert (append) at the end of the word
Esc - exit insert mode```
``` bash
The Difference Between Soft and Hard Links

Hard links
- Only link to a file not a directory
- Can not reference a file on a different disk/volume
- Links will reference a file even if it is moved
- Links reference inode/physical locations on the disk

Symbolic (soft) links

- Can link to directories
- Can reference a file/folder on a different hard disk/volume
- Links remain if the original file is deleted
- Links will NOT reference the file anymore if it is moved
- Links reference abstract filenames/directories and NOT physical locations. They are given their own inode

Example 1:

$ ln -s /Users/carlossantiagocruz/Documents/BASH-PROGRAMMING/DICT-EN-ES/trad3.sh /usr/local/bin/trad3

Example 2:

ln -s /Users/carlossantiagocruz/Documents/BASH-PROGRAMMING/MOVER-PDF-2-DIRECTORIO/mover-pdf2directorio.sh /usr/local/bin/mover-pdf2directorio1.0```
``` bash
Which file permission to write to text files?

0755 for directories
0644 for files
```
``` bash

1
down vote
The play command from the sox package will play any file format supported by sox

To install sox open terminal and run:

sudo apt-get install sox
sudo apt-get install sox libsox-fmt-all
To use play command:

play file_name.extension
Use man sox for more information
```
``` bash
                                                                                                                                                  1   help



How do I make a Mac Terminal pop-up/alert? Applescript?




I want to be able to have my program display an alert, notice, whatever that displays my custom text. How is this done? Also, is it possible to
make one with several buttons that sets a variable?

Similar to batch's:         echo msgbox""<a.vbs&a.vbs


 osx    popup       terminal      applescript   alert


 asked Apr 7 '11 at 21:48
        JShoe
        872     5    22      43



7 Answers


Use    osascript         . For example:

osascript -e 'tell app "Finder" to display dialog "Hello World"'


Replacing “Finder” with whatever app you desire. Note if that app is backgrounded, the dialog
will appear in the background too. To always show in the foreground, use “System Events” as
the app:

osascript -e 'tell app "System Events" to display dialog "Hello World"'


Read more on Mac OS X Hints.

        edited Sep 9 '15 at 13:54                                answered Apr 7 '11 at 22:20
        Andrew Marshall                                                  Anne
        65.4k       12     142    160                                    21.2k   7   46   65


    Wait, you can abbreviate application as app? – JShoe Apr 7 '11 at 22:23

    The AppleScript engine will automatically replace it. Simply paste the line between the quotes in AppleScript
    Editor, when you hit Run, it replaces app automatically with application before execution. – Anne Apr 7 '11 at
    22:27

2   SWEET!!! Thanks again! – JShoe Apr 7 '11 at 22:28

    Another typing saver: you don't need "end if", "end repeat", etc., just "end" is fine and AppleScript will insert
    the second word. – Nicholas Riley Apr 8 '11 at 0:04

3   If you don't want the "Cancel" button but just want an "OK" button replace {dialog} with {alert}. – Bart B Jul
    26 '13 at 2:07




If you're using any Mac OS X version which has Notification Center, you can use the terminal-
notifier gem. First install it (you may need sudo ):

gem install terminal-notifier


and then simply:

terminal-notifier -message "Hello, this is my message" -title "Message Title"


See also this OS X Daily post.
        edited Sep 9 '15 at 13:58                               answered Sep 26 '12 at 8:14
        Andrew Marshall                                                Enrico Carlesso
        65.4k    12    142        160                                  4,307   2    25   39


4   This is simply so much better than the old osascript stuff. – Jonny Nov 13 '12 at 11:06

    This appears to not work in 10.7.5 (Lion), apparently no Notification Center in it. – Norman H Dec 27 '12 at
    18:32

    this allows you to play a sound too, so.... nice! – Brad Parks Sep 19 '14 at 11:53

    brew install terminal-notifier also works if you prefer to brew. – gklka May 2 '15 at 17:40

    PSA: On Mavericks and later this isn't needed, just use osascript's display notification, which is mentioned
    below in Pradeep's answer. – alexchandel Jun 23 '16 at 22:57




Use this command to trigger the notification center notification from the terminal.

osascript -e 'display notification "Lorem ipsum dolor sit amet" with title "Title"'


        answered Jul 7 '14 at 8:10
        Pradeep Vairamani
        1,352    1    15     36




This would restore focus to the previous application and exit the script if the answer was
empty.

a=$(osascript -e 'try
tell app "SystemUIServer"
set answer to text returned of (display dialog "" default answer "")
end
end
activate app (path to frontmost application as text)
answer' | tr '\r' ' ')
[[ -z "$a" ]] && exit


If you told System Events to display the dialog, there would be a small delay if it wasn't running
before.

For documentation about display dialog, open the dictionary of Standard Additions in
AppleScript Editor or see the AppleScript Language Guide.

 answered Sep 26 '12 at 11:20
        user495470
        14.7k    5    48     59




And my 15 cent. A one liner for the mac terminal etc just set the MIN= to whatever and a
message

MIN=15 && for i in $(seq $(($MIN*60)) -1 1); do echo "$i, "; sleep 1; done; echo -e
"\n\nMac Finder should show a popup" afplay /System/Library/Sounds/Funk.aiff;
osascript -e 'tell app "Finder" to display dialog "Look away. Rest your eyes"'


A bonus example for inspiration to combine more commands; this will put a mac put to standby
sleep upon the message too :) the sudo login is needed then, a multiplication as the 60*2 for
two hours goes aswell

sudo su
clear; echo "\n\nPreparing for a sleep when timers done \n"; MIN=60*2 && for i in
$(seq $(($MIN*60)) -1 1); do printf "\r%02d:%02d:%02d" $((i/3600)) $(( (i/60)%60))
$((i%60)); sleep 1; done; echo "\n\n Time to sleep zzZZ"; afplay
/System/Library/Sounds/Funk.aiff; osascript -e 'tell app "Finder" to display dialog
"Time to sleep zzZZ"'; shutdown -h +1 -s


 edited Dec 26 '15 at 15:40                                     answered Oct 7 '14 at 9:38
                                                                       K Lindberg
                                                                       1,272   9    24




A simular question and answer is available at: http://superuser.com/questions/246353/how-to-
make-the-terminal-do-a-pop-up-alert-in-osx
 answered Apr 7 '11 at 21:51
        Mark
        204    1   2


  Similar title, yes, but different question. I want to make a window that appears that requires user interaction
  (hitting a button) to then close. – JShoe Apr 7 '11 at 22:14

  +1 - The answers suggested there worked perfectly for me. – ArtOfWarfare Sep 24 '13 at 18:08

  While this link may answer the question, it is better to include the essential parts of the answer here and
  provide the link for reference. Link-only answers can become invalid if the linked page changes. - From
  Review – Polygnome May 13 '16 at 9:15




I made a script to solve this which is here. You don't need any extra software for this.
Installation:
brew install akashaggarwal7/tools/tsay
Usage:
sleep 5; tsay

Feel free to contribute!

 answered Oct 15 '16 at 15:11
        Akash Aggarwal
        884    5   29
```
``` bash
cat removeAllFiles.txt
Para remover el directorio llamado /tmp/foo/ y todos los archivos contenidos en el mismo, incluyendo a los subdirectorios, debemos también usar el comando rm, como por ejemplo:

rm -rf /tmp/foo/
```
``` bash
Search and replace

/pattern - search for pattern
?pattern - search backward for pattern
\vpattern - 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)
n - repeat search in same direction
N - repeat search in opposite direction
:%s/old/new/g - replace all old with new throughout file
:%s/old/new/gc - replace all old with new throughout file with confirmations
:noh - remove highlighting of search matches```
``` bash
sed 's/Nick/John/g' report.txt          Replace every occurrence of Nick with John in report.txt
sed 's/Nick|nick/John/g' report.txt     Replace every occurrence of Nick or nick with John.
sed 's/^/ /' file.txt >file_new.txt     Add 8 spaces to the left of a text for pretty printing.
sed -n '/Of course/,/attention you \pay/p' myfile       Display only one paragraph, starting with "Of course" and ending in "attention you pay"
sed -n 12,18p file.txt                  Show only lines 12-18 of file.txt
sed G file.txt                          Double-space file.txt
sed -f script.sed file.txt              Write all commands in script.sed and execute them
sed '5!s/ham/cheese/' file.txt          Replace ham with cheese in file.txt except in the 5th line
sed '$d' file.txt                       Delete the last line
sed '/[0-9]\{3\}/p' file.txt            Print only lines with three consecutive digits
sed '/boom/!s/aaa/bb/' file.txt         Unless boom is found replace aaa with bb
sed '17,/disk/d' file.txt               Delete all lines from line 17 to 'disk'
echo ONE TWO | sed "s/one/unos/I"       Replaces one with unos in a case-insensitive manner, so it will print "unos TWO"
sed 'G;G' file.txt                      Triple-space a file
sed 's/.$//' file.txt                   A way to replace dos2unix :)
sed 's/^[ ^t]*//' file.txt              Delete all spaces in front of every line of file.txt
sed 's/[ ^t]*$//' file.txt              Delete all spaces at the end of every line of file.txt
sed 's/^[ ^t]*//;s/[ ^]*$//' file.txt   Delete all spaces in front and at the end of every line of file.txt
sed 's/^[ ^t]*//;s/[ ^]*$//' file.txt   Delete all spaces in front and at the end of every line of file.txt
sed 's/foo/bar/' file.txt               Replace foo with bar only for the first instance in a line.
sed 's/foo/bar/4' file.txt              Replace foo with bar only for the 4th instance in a line.
sed 's/foo/bar/g' file.txt              Replace foo with bar for all instances in a line.
sed '/baz/s/foo/bar/g' file.txt         Only if line contains baz, substitute foo with bar
sed '/./,/^$/!d' file.txt               Delete all consecutive blank lines except for EOF
sed '/^$/N;/\n$/D' file.txt             Delete all consecutive blank lines, but allows only top blank line
sed '/./,$!d' file.txt                  Delete all leading blank lines
sed -e :a -e '/^\n*$/{$d;N;};/\n$/ba' \ file.txt        Delete all trailing blank lines
sed -e :a -e '/\$/N; s/\\n//; ta' \ file.txt            If a file ends in a backslash, join it with the next (useful for shell scripts)
sed '/regex/,+5/expr/'                                  Match regex plus the next 5 lines
sed '1~3d' file.txt                                     Delete every third line, starting with the first
sed -n '2~5p' file.txt                                  Print every 5th line starting with the second
sed 's/[Nn]ick/John/g' report.txt                       Another way to write some example above. Can you guess which one?
sed -n '/RE/{p;q;}' file.txt                            Print only the first match of RE (regular expression)
sed '0,/RE/{//d;}' file.txt                             Delete only the first match
sed '0,/RE/s//to_that/' file.txt                        Change only the first match
sed 's/^[^,]*,/9999,/' file.csv                         Change first field to 9999 in a CSV file
sed ':a;s/\(^\|[^0-9.]\)\([0-9]\+\)\([0-9]\{3\}\)/,/g;ta' file.txt          Change numbers from file.txt from 1234.56 form to 1.234.56
sed -r "s/\<(reg|exp)[a-z]+/\U&/g"                      Convert any word starting with reg or exp to uppercase
sed '1,20 s/Johnson/White/g' file.txt                   Do replacement of Johnson with White only on lines between 1 and 20
sed '1,20 !s/Johnson/White/g' file.txt                  The above reversed (match all except lines 1-20)
sed '/from/,/until/ { s/\<red\>/magenta/g; \s/\<blue\>/cyan/g; }' file.txt          Replace only between "from" and "until"
echo "Welcome to LikeGeeks page" | sed 's/page/website/'                            stdout: Welcome to LikeGeeks website

```
``` bash
The tr command automatically translates (substitutes, or maps) one set of characters to another.

$ echo 'linux' | tr "[:lower:]" "[:upper:]"
$ echo 'linux' | tr "a-z" "A-Z"
$ echo 'I LovE linuX. one is better Than 2' | tr "a-z" "A-Z"

-d option removes all occurrences of characters that have been specified:

$ echo "Can you see how tr command can be wonderful?" | tr -d "cawe?" 
Cn you s ho tr ommnd n b ondrful

echo "Can you see how tr command can be won----derful?" | tr -d "-"
Can you see how tr command can be wonderful?

echo uppercaseme | tr '[:lower:]' '[:upper:]'
UPPERCASEME

echo 'too    many    spaces  here' | tr -s '[:space:]'
too many spaces her

echo "some_url_that_I_have" | tr "_" "-"
some-url-that-I-have

echo Bad\ File\ nAme.txt | tr -d '\' | tr ' ' '_' | tr '[:upper:]' '[:lower:]'
bad_file_name.txt

echo "my password is 432234" | tr -cd [:digit:]
432234

```
``` bash
I used the following commands to convert

ffmpeg -i movie.webm movie.mp4
ffmpeg -i movie.webm -vcodec libx264 movie.mp4
ffmpeg -i movie.webm -vcodec libx264 -qscale 0 movie.mp4
```
``` bash
Use wget To Download All Files Located On A Web Page With Windows 7:
wget -r -A.pdf http://www.example.com/page-with-pdfs.htm

```
``` bash
If all of the videos are in the same playlist or the same channel, you can save time by using the following shortcuts.

Playlist

youtube-dl -f FORMAT -ci <url-of-playlist>

example:

youtube-dl -f mp4 -ci https://www.youtube.com/channel/UCx7yEPUZLfHhbqqFDHmfXuw

youtube-dl -f mp4 -ci https://www.youtube.com/watch?v=qbBAqaf6cIg


```
