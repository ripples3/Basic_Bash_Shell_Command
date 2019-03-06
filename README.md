# Basic_Bash_Shell_Command
Guide for learning basic bash shell command
## Table of Contents
  1. [Basic Operations](#1-basic-operations)  
    1.1. [File Operations](#11-file-operations)  
    1.2. [Text Operations](#12-text-operations)  
    1.3. [Directory Operations](#13-directory-operations)  
    1.4. [SSH, System Info & Network Operations](#14-ssh-system-info--network-operations)  
    1.5. [Process Monitoring Operations](#15-process-monitoring-operations)
  2. [Basic Shell Programming](#2-basic-shell-programming)  
    2.1. [Variables](#21-variables)  
    2.2. [Array](#22-array)  
    2.3. [String Substitution](#23-string-substitution)  
    2.4. [Functions](#24-functions)  
    2.5. [Conditionals](#25-conditionals)  
    2.6. [Loops](#26-loops)  
  3. [Tricks](#3-tricks)  
  4. [Debugging](#4-debugging)  
  

# 1. Basic Operations

### a. `export`
Displays all environment variables. If you want to get details of a specific variable, use `echo $VARIABLE_NAME`.  
```bash
export
```
Example:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
whatis shows description for user commands, system calls, library functions, and others in manual pages
```bash
whatis something
```
Example:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
whereis searches for executables, source files, and manual pages using a database built by system automatically.
```bash
whereis name
```
Example:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
which searches for executables in the directories specified by the environment variable PATH. This command will print the full path of the executable(s).
```bash
which program_name 
```
Example:
```bash
$ which php
/c/xampp/php/php
```

### e. clear
Clears content on window.


## 1.1. File Operations
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>


### a. `cat`
It can be used for the following purposes under UNIX or Linux.  
* Display text files on screen
* Copy text files  
* Combine text files  
* Create new text files  
```bash
cat filename
cat file1 file2 
cat file1 file2 > newcombinedfile
cat < file1 > file2 #copy file1 to file2
```

### b. `chmod`
The chmod command stands for "change mode" and allows you to change the read, write, and execute permissions on your files and folders. For more information on this command check this [link](https://ss64.com/bash/chmod.html).
```bash
chmod -options filename
```

### c. `chown`
The chown command stands for "change owner", and allows you to change the owner of a given file or folder, which can be a user and a group. Basic usage is simple forward first comes the user (owner), and then the group, delimited by a colon.
```bash
chown -options user:group filename
```

### d. `cp`
Copies a file from one location to other.  
```bash
cp filename1 filename2
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.

### e. `diff`
Compares files, and lists their differences.  
```bash
diff filename1 filename2
```

### f. `file`
Determine file type.  
```bash
file filename
```
Example:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Find files in directory
```bash
find directory options pattern
```
Example:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `head`
Outputs the first 10 lines of file  
```bash
head filename
```

### i. `tail`
Outputs the last 10 lines of file. Use `-f` to output appended data as the file grows.  
```bash
tail filename
```

### j. `lpq`
Check out the printer queue.  
```bash
lpq
```
Example:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```


### k. `ls`
Lists your files. `ls` has many options: `-l` lists files in 'long format', which contains the exact size of the file, who owns the file, who has the right to look at it, and when it was last modified. `-a` lists all files, including hidden files. For more information on this command check this [link](https://ss64.com/bash/ls.html).  
```bash
ls option
```
Example:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### l. `more`
Shows the first part of a file (move with space and type q to quit).  
```bash
more filename
```

### m. `mv`
Moves a file from one location to other.  
```bash
mv filename1 filename2
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.

Also it can be used for rename a file.
```bash
mv old_name new_name
```

### n. `rm`
Removes a file. Using this command on a directory gives you an error.
`rm: directory: is a directory`
To remove a directory you have to pass `-r` which will remove the content of the directory recursively. Optionally you can use `-f` flag to force the deletion i.e. without any confirmations etc.
```bash
rm filename
```

### o. `touch`
Updates access and modification time stamps of your file. If it doesn't exists, it'll be created.
```bash
touch filename
```
Example:
```bash
$ touch trick.md
```

### p. `sed`
Perform functions on file such as searching, find and replace, insertion or deletion.  
```
#Replacing or substituting string
$sed 's/unix/linux/' geekfile.txt
```

### p. `gunzip`
Un-compresses files compressed by gzip.  
```bash
gunzip filename
```

### q. `gzcat`
Lets you look at gzipped file without actually having to gunzip it.  
```bash
gzcat filename
```

### r. `gzip`
Compresses files.  
```bash
gzip filename
```
