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
