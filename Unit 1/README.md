# Unit 1: Overview of Linux
## Basic commands
### change directory(cd)
#### types of cd
```
syntax : cd <options> <directory>
cd ~ #change to your home directory
cd / #change to root directory
cd .. #change to parent directory
cd - #change to previous directory where you were working earlier
example:  
cd ~/Documents
```
###man command
```
this command is used to display the man page entry that explains a given command
syntax : man <commandname>
example: man ls
```
### ls command (list the content)
```
syntax : ls <option> <directory>
```
#### types of option in ls
```
-a : list all files including hidden files starting with '.'
-d : List directory
-l : list with long format 
-r : list in reverse order
-s : sort by size
-t : sort by time and date 
-X : sort by extension name
-R : list the file and folder of directory and sub directory
-C : list entries by columns
-i : print inode number of each file
```
### cp (copy the content)
syntax : cp <option> <source-file> <destination-file>
#### types of option in ls
```
-a : archive files
-f : force copy by removing destination file
-n : do not overwrite an existing file
-R : recursive copy
-v : print information message
-i : prevent cp from overwriting existing files
-p : preserve all information,including owner,group and permissions
example: to copy multiple files using cp cmd, pass the names of files followed by destination directory
cp file1 file2 file3 dir1
```
###rm (remove files or directory)
syntax : rm <options> <filename>
#### types of option in rm
```
-i : prompt before every removal
-I : prompt once before removing more than 3 files
-r,-R : remove directories and their contents recursively
-d : Remove empty directories
-f : remove write-protected file, never prompt before removing
-v : explain what is being(print name of each file before removing)
example: remove directory and any files it contains
rm -r mydirectory
### mkdir (create a new directory)
syntax : mkdir <option> <directory-name>
```
#### types of option in mkdir
```
-m : set permission mode
-p : create parent directories as necessary
-v : print a message for each created directory
example: to create several subdirectories at one time
mkdir -p first/second/third
```
### rmdir (remove the directory)
```
syntax : rmdir <options> <directoryname>
```
#### types of option in rmdir
```
-v : print a message for every directory processed
-p : each of directory argument is treated as a pathname or which all components with be removed.
example : to delete nested empty directories 
rmdir -p first/second/third 
```
### pwd(presend working directory)
```
syntax: pwd <option>
```
#### types of option in pwd
```
-L : display the content as absolute name
-P : print fully resolved name for current directory
```
### file
```
syntax:file <option> <filename>
```
#### types of option in file
```
-b : to show just the file type
-i : to view the mime type of a file
-F : file and file type are seperated by :
-s : used for special files
z : to view compressed files without decompressing
example:to see the file type without filename
file -b sample.txt
```
### more
```
syntax: more <filename>
```
#### types of option in more
```
-d : prompt the user with the message "[press space to continue,q to quit]" and will display "[press h for instructions.]"
-s : squeeze multiple blank lines into one
-u : omits the underlines
-NUM : specify the number of lines per screenful
+NUM : Display file beginning from line number NUM
example : 
more sample.txt
to display man page of ls command page by page.
man ls|more
```
### less
```
syntax : less <filename>
```
#### types of option in less
```
-F : causes less to exit if entire file can be displayed on first screen
-s : squeeze multiple blank lines into one.
-u : omits the underlines.
-n : suppress line number
example:
less sample.txt
man ls|less
```
### cat(concatenate)
```
syntax:cat<options><filename>
```
#### types of option in cat
```
-b : add line number to non-blank lines
-n : add line number to all lines
-s : suppress repeated empty output lines
-E : display $ at end of each line
example: to append content of one file to another 
cat filename1>>filename2
```
## File comparison commands
###cmp(compare)
```
syntax: cmp <options> <filename1> <filename2>
```
####types of options in cmp
```
-b : displays the differing bytes in the output
-i : skip a particular number of initial bytes from both the files and then after skipping it compares the files.
-i SKIP1:SKIP2 : skip the first SKIP1 bytes of File1 and the first SKIP2 bytes of File2
-l : print byte position and byte value for all differing bytes
-s : suppress all normal output,print exit statement only.
-n[no. of bytes] : limit the number of bytes you want to compare
example: this command compares first 50 bytes
cmp -n 50 file1 file2
```
###diff(difference)
```
syntax: diff [options] <filename1> <filenam2>
```
####types of options in diff
```
-i : ignore case differences in file contents
-b : ignore changes in amount of white space
-w : ignore all white spaces
-q : prompt when two files are differ
-s : report when two files are the same
```
#### two different ways to view diff command
```
* Context mode(-c) 
* Unified mode(-u)
```
###comm(compare two sorted files line by line)
```
syntax : comm<options> <file1> <file2>
```
#### types of option in comm
```
-1 : suppress column 1
-2 : suppress column 2
-3 : suppress column 3
example: this cmd suppresses column 1
comm -1 file1 file2
```
### uniq
```
syntax : uniq [option] <filename>
```
####types of options in uniq
```
-d : displays only the duplicate lines
-u : displays only unique lines
-i : case-sensitive comparisons
-c : displays line by eliminating duplicate lines and prefix lines with a number representing how many times they occured.
-w : only compares N characters in a line 
```