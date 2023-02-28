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
