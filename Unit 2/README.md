# ESSENTIAL LINUX COMMANDS

```
background processes can be ran using an & at the end of cmd.
example: cp sample samplecopy &

listing all files and directories and give it as input for more cmds
example: ls -1|more

using sort and uniq cmd to sort and print unique values
example: sort fil1|uniq
```
### tee command
```
syntax : command1|command2|..|tee <filename>
example: sort file1|uniq|tee sortfile
```
### overwrite
```
> - standard output
< - standard input
2> - standard error
example : cat sample > test
more < file1
cat myfile 2> errorfile
```
### append
```
>> - standard output
<< - standard input
2>> - standard error
example : 
```
### Job Control commands
```
Jobs :- list all active jobs
bg%n :- places all the current or specified job in the background,where n is the job ID
fg%n :- brings the current or specified job into the foreground
Control-Z :- stops the foreground job and places it in the background as a stopped job
atq :- to display all the at cmd jobs that are scheduled
atrm:- to delete a particular job
```
### options for job cmd
```
-1 : for listing the submitted jobs
-r : for removing a submitted job
```
### cron scheduling 
#### at
```
this cmd used to execute cmd at future date and time
at <time>
at> <commands>
^d (press ctrl+d at the end)
example : at 12:30 PM
```
### batch 
```
this cmd is used to execute specified cmds when system load is tight
syntax : batch <commands> ^d
example : batch
            sort file1
            sort file2
            cp sample samplecopy
            ^d
```
### nohup 
```
if a user wants to process that he has executed not to die even when he logged-out from the system.
syntax : nohup <command> &
example : nohup sort file1 &
```
### kill
```
syntax : kill [-signal number] <PID>
example : kill 120
            kill -9 0
```
### ps (process status)
```
cmd to show which process are running in the system
syntax : ps [options]
```
#### options in ps
```
-A,-e : viewing all the running process
-T : select all processes on the terminal
-a : to view all the processes with the exception of processes associated with the terminal 
-u <user-name> : list the processes which are running for the specified user
-t <terminal-name> : lists the processes which are running on the specified terminal
-x : lists the system processes
``` 
### who
```
display the users who are logged on the system currently
syntax : who[options]
example : who am i
```
#### options in who
```
-b : the time of last system boot
-a : lists all available output for each user 
-d : Display dead processes
-H : print line of column headings
-1 : print system login processes
-q : print all login names and number of users logged on
-s : print only name, line , and time(default)
-t : print the last time the system clock was changed.
```
### find 
```
locating files which meet the search criteria
syntax : find <path-list> <selection-criteria> <action>
example: find -name sample -print
            find /home -name *.txt -print
```
#### selection criteria in find
```
-name <filename> : select the file specified in <filename>
-user <username> : select the file owned by <username>
-type d : select directories
-size +n or -n : select files greater than/less than "n" blocks
-mtime n or +n or -n : select files that have been modified on exactly n days/more than n days/ less than n days
-mmin n or +n or -n : select files that have been modified on exactly n minutes/more than n minues/ less than n minutes
-atime n or +n or -n : select files that have been accessed on exactly n days/ more than n/ less than n days
-amin n or +n or -n : select files that have been accessed on exactly n minutes/ more than n/ less than n minutes
-empt : Returns true if a file is empty
```
#### the "action" maybe as follows
```
-print : displays the selected files on the screen
-exec <command> : Execute the specified Linux commands ends with {}\;
-delete : Delete files
```
### sort
```
sort the contents of a given file
syntax : sort [options] <filename>
example : sort -o sortfile file1
```
#### options in sort
```
-m <filelist> : merges sorted files specified <filelist>
-o <filename> : stores output in the specified <filename>
-r : sorts the content in reverse order
-u : removes the duplicate lines and display
-n : Numeric-sort 
-c : checks if the file is sorted or not.
-f : ignore case
-b : ignore leading spaces
+pos : starts sorting after skipping pos field
-pos : stops sorting after pos filed
-t "char" : uses the specified "char" as delimiter
```
### touch
```
this is used to create empty files
syntax : touch [options] <filename>[filename2...]
example : touch -a sample
```
#### options in touch
```
-a : change only the access time
-c : if the file does not exist, do not create it
-m : Change only the modification Time
-r : use the access and modifications times of file
-t : creates file using specified time
```
### file 
```
determine the type of file
syntax : file [options] <filename>
example : file -i file1
```
#### options in file
```
-b : Display just file type in brief mode
-i : output mime type strings rather than more traditional human readable ones.
-s : For special files
```
## File processing commands
### wc 
```
display the number of lines, words and characters
syntax : wc [-options] <filename>
example : wc file1 file2 file3
```
#### options in wc
```
-1 : displays the number of lines in the file
-w : displays the number of words in the file
-c : displays the number of bytes in file
-m : displays the number of characters in file
```
### cut
```
cut the column/fields of a specified file
syntax : cut [option] <filename>
example : cut -d " " -f 1sample
```
#### options in cut 
```
-b : select only these bytes
-c : select only these characters
-f : select only these fields
-d DELIM : use character DELIM instead of a tab 
```
### paste 
```
concatenates the contents of the specified files
syntax : paste <filename1> <filename2>
example : paste -d "." state capital
```
#### options in paste
```
-s : paste one file at a time
-d DELIM : use character DELIM as delimiter instead of tab
```
## Mathematical Commands
### expr
```
used to perform arithmetic operations on integers
syntax : expr expression 
example : expr 10 - 5
```
### bc (basic calculator)
```
perform arithmetic operations on integers as well as on floating point numbers
example : bc
            10 + 5.5
            15.5
```
### factor
```
used to print the prime factors of a number
syntax : factor [number]
example : factor 30
output:          30: 2 3 5
```
## VI editor
```
The default editor that comes with the UNIX operating system is called vi (visual editor). Using vi editor, we can edit an existing file or create a new file from scratch. we can also use this editor to just read a text file. 
syntax : vi <filename>
example : vi file1 
```
#### symbols in VI
```
l : move one character right
h : move one character left
j : move one line down
k : move one line up
<space> : move one character right
G : Go to last line of the file
<n>G : Go to line number n in the file
$ :  Go to end of current file
^ : Go to start of the file
w : Go to beginning of the next file
b : Go to beginning of the previous file
e : move to end of word
H : Go to first line of screen
M : Go to middle line of screen
L : Go to last line of screen
( : GO to beginning of sentence
) : GO to end of sentence
{ : GO to beginning of paragraph
} : GO to end of paragraph
```
### inserting and deleting Text
#### List of text entry commands
```
i : Start inserting text at current cursor location
I : Start inserting text at beginning of current line
a : appends after cursor 
A : appends at end of the current line
o : inserting blank line just below the current line
O : inserting blank line just above current line and start inserting text from beginning
```
#### list of text delete commands
```
x :  delete character starting at current cursor location
<n> x : delete n characters starting at current cursor location
X : delete previous character from the current cursor location
<n> X : delete n previous characters from the current cursor location
dd : Delete current line
db : Delete previous word
dw : delete from current cursor location to end of word
dG : delete to end of file including current line.
```
#### replacing Text
```
r : Replace current character remaining in command mode
R : replace multiple characters until the Esc key is pressed
s : replace current character and go to insert mode
S : replaces the entire line
cw : change to beginning of next word
cc : removes content of file
cG : change to end of file
```
#### search and replace 
```
/text : search text in forward direction starting from current cursor location
?text : search text in backward direction starting from current cursor location
/ : repeat previous search in forward direction
? : Repeat previous search in backward direction
n : repeat search in same direction
N : repeat search in the opposite direction
:s/oldtext/newtext :  search oldtext in the forward direction and replace with newtext
:s/oldtext/newtext/g : search oldtext in the entire file and replace with newtext
:m,n s/oldtext/newtext : search oldtext in the forward direction from line m to line n and replace with newtext
/text : if you put space between the / and the text to be searched,only whole words are searched
/^text : search text only in the beginning of a file
/text$ : search text only in the end of a file
/(More than one word) : use parenthesis to search multiple words
```
### cut,copy,paste commands
```
yy : copy or yank current line
<n> yy : copy n lines starting from current line position
p : paste yanked text after the current cursor postion 
P : paste yanked text before the current cursor postion  
:m <a> : move current line and paste after line number a
:<a>,<b> m <c> : move lines from  a to b and paste after line number c
:<a>,<b> t <c> : copy lines from a to b and paster after line number c
```
### set commands
```
:set number : sets line number in front of each line in Vi
:set all : lists all available options
:set autoindent : the next line is indented the same number
:set readonly : sets the current file as read-only.
:set wrapmargin = n : sets the right wrap margin equal to n.If we are using 80-column display and the wrap margin is set to 6, every line will be wrapped to the next line after 74 characters
:set showmode : Displays the currently working mode
```
### Running commands 
```
vi can run commands from within the editor
syntax : :!<command>
```
