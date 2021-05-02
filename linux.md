# Table of Contents
<!-- TOC -->autoauto- [Table of Contents](#table-of-contents)auto- [**Command Line**](#command-line)auto    - [Command Line and Sheel](#command-line-and-sheel)auto    - [Sheel Command Structure](#sheel-command-structure)auto    - [Basic Sheel Commands](#basic-sheel-commands)auto        - [Manual Pages](#manual-pages)auto        - [Manual Structure](#manual-structure)auto        - [How to read the synopsis](#how-to-read-the-synopsis)auto    - [Vi Text Editor](#vi-text-editor)auto    - [Wildcards](#wildcards)auto        - [Basic set of wildcards](#basic-set-of-wildcards)auto        - [Example](#example)auto    - [Permissions](#permissions)auto        - [Types of permissions](#types-of-permissions)auto        - [Permissions subjects](#permissions-subjects)auto- [**Bash Scripting**](#bash-scripting)auto    - [Variables](#variables)auto        - [Special variables](#special-variables)auto    - [Input](#input)auto    - [Operations](#operations)auto        - [let](#let)auto        - [expr](#expr)auto        - [Double parentheses](#double-parentheses)auto        - [Length of a variable](#length-of-a-variable)auto    - [Conditionals](#conditionals)auto        - [If statements](#if-statements)auto        - [Case Statements](#case-statements)auto        - [Test](#test)auto        - [Boolean Operations](#boolean-operations)auto    - [Loops](#loops)auto        - [While loops](#while-loops)auto        - [Until loops](#until-loops)auto        - [For loops](#for-loops)auto        - [Break and continue](#break-and-continue)auto        - [Select](#select)auto    - [Funtions](#funtions)auto        - [Local variable](#local-variable)auto        - [Overriding commands](#overriding-commands)autoauto<!-- /TOC -->

------------------------------------------
# **Command Line**

The command line is a text interface for your computer. It’s a program that takes in commands, which it passes on to the computer’s operating system to run.

## Command Line and Sheel

A shell is a computer program that presents a command line interface which allows you to control your computer using commands entered with a keyboard instead of controlling graphical user interfaces (GUIs) with a mouse/keyboard combination.

On a Mac or Linux machine, you can access a shell through a program called Terminal, which is already available on your computer. If you’re using Windows, you’ll need to download a separate program to access the shell.

## Sheel Command Structure

A command is a program that tells the Unix system to do something. Where an argument indicates on what the command is to perform its action, usually a file or series of files. An option modifies the command, changing the way it performs.

Commands are case sensitive, **command** and **Command** are not the same.

```
Key Points

- The shell gives you the ability to work more efficiently by using keyboard commands rather than a GUI.
- Useful commands for navigating your file system include: ls, pwd, and cd.
- Most commands take options (flags) which begin with a -.
- Tab completion can reduce errors from mistyping and make work more efficient in the shell.
```

## Basic Sheel Commands

A shell is a special user program that provides an interface to the user to use operating system services.

* Displaying the file contents on the terminal: 
    * `cat` : It is generally used to concatenate the files. 
    * `more` : It is a filter for paging through text one screenful at a time.
    * `less` : It is used to viewing the files instead of opening the file.
    * `head` : Used to print the first N lines of a file. 
    * `tail` : Used to print the last N-1 lines of a file. 

* File and Directory Manipulation Commands: 
    * `mkdir` : Used to create a directory if not already exist.
    * `cp` : This command will copy the files and directories from the source path to the destination path. 
    * `mv` : Used to move the files or directories. This command’s working is almost similar to cp command but it deletes a copy of the file or directory from the source path.
    * `rm` : Used to remove files or directories.
    * `touch` : Used to create or update a file.

* Extract, sort, and filter data Commands: 
    * `grep` : This command is used to search for the specified text in a file.

    * `grep with Regular Expressions` : Used to search for text using specific regular expressions in file. Example : 
        ```
        grep -E ^Er Language
        ```
    * `sort` : This command is used to sort the contents of files.
    * `wc` : Used to count the number of characters, words in a file.
    * `cut` : Used to cut a specified part of a file.

* Basic Terminal Navigation Commands: 
    * `ls` : To get the list of all the files or folders.
    * `ls -l` : Optional flags are added to ls to modify default behavior, listing contents in extended form -l is used for “long” output
    * `ls -a` : Lists of all files including the hidden files, add -a  flag 
    * `cd` : Used to change the directory.
    * `du` : Show disk usage.
    * `pwd` : Show the present working directory.
    * `man` : Used to show the manual of any command present in Linux.
    * `rmdir` : It is used to delete a directory if it is empty.
    * `ln file1 file2` : Creates a physical link.
    * `ln -s file1 file2` : Creates a symbolic link.
    * `locate` : It is used to locate a file in Linux System
    * `echo` :  This command helps us move some data, usually text into a file.
    * `df` : It is used to see the available disk space in each of the partitions in your system.
    * `tar` : Used to work with tarballs (or files compressed in a tarball archive)

* File Permissions Commands: The chmod and chown commands are used to control access to files in UNIX and Linux systems. 
    * `chown` : Used to change the owner of the file.
    * `chgrp` : Used to change the group owner of the file.
    * `chmod` : Used to modify the access/permission of a user.

### Manual Pages

The man page(manual page) is a documentation manual of different commands available in unix or unix like operating systems. To check manual entry for any command use, `man command_name`. 

Example :
```
man printf
```

Output :
```
PRINTF(1)                        User Commands                       PRINTF(1)

NAME
       printf - format and print data

SYNOPSIS
       printf FORMAT [ARGUMENT]...
       printf OPTION

DESCRIPTION
       Print ARGUMENT(s) according to FORMAT, or execute according to OPTION:

       --help display this help and exit

       --version
              output version information and exit

       FORMAT controls the output as in C printf.  Interpreted sequences are:

       \"     double quote

       \\     backslash

       \a     alert (BEL)

       \b     backspace

       \c     produce no further output

       \e     escape

       \f     form feed

       \n     new line

       \r     carriage return

       \t     horizontal tab

       \v     vertical tab

       \NNN   byte with octal value NNN (1 to 3 digits)

       \xHH   byte with hexadecimal value HH (1 to 2 digits)

       \uHHHH Unicode (ISO/IEC 10646) character with hex value HHHH (4 digits)

       \UHHHHHHHH
              Unicode character with hex value HHHHHHHH (8 digits)

       %%     a single %

       %b     ARGUMENT  as  a  string with '\' escapes interpreted, except that octal escapes are of the
              form \0 or \0NNN

       %q     ARGUMENT is printed in a format that can be reused as shell input, escaping  non-printable
              characters with the proposed POSIX $'' syntax.

       and  all  C  format  specifications ending with one of diouxXfeEgGcs, with ARGUMENTs converted to
       proper type first.  Variable widths are handled.

       NOTE: your shell may have its own version of printf, which usually  supersedes  the  version  de‐
       scribed  here.   Please refer to your shell's documentation for details about the options it sup‐
       ports.

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report printf translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2018 Free Software Foundation, Inc.  License GPLv3+:  GNU  GPL  version  3  or  later
       <https://gnu.org/licenses/gpl.html>.
       This  is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the
       extent permitted by law.

SEE ALSO
       printf(3)

       Full documentation at: <https://www.gnu.org/software/coreutils/printf>
       or available locally via: info '(coreutils) printf invocation'

GNU coreutils 8.30                           September 2019                                    PRINTF(1)
```

Example of PRINTF, for all entries, try below command:
```
man -a printf
```
Output :
```
PRINTF(1)                        User Commands                       PRINTF(1)

NAME
       printf - format and print data

SYNOPSIS
       printf FORMAT [ARGUMENT]...
       printf OPTION

DESCRIPTION
       Print ARGUMENT(s) according to FORMAT, or execute according to OPTION:

       --help display this help and exit

       --version
              output version information and exit

       FORMAT controls the output as in C printf.  Interpreted sequences are:

       \"     double quote

       \\     backslash

       \a     alert (BEL)

       \b     backspace

       \c     produce no further output

       \e     escape

       \f     form feed

       \n     new line

       \r     carriage return

       \t     horizontal tab

       \v     vertical tab

       \NNN   byte with octal value NNN (1 to 3 digits)

       \xHH   byte with hexadecimal value HH (1 to 2 digits)

       \uHHHH Unicode (ISO/IEC 10646) character with hex value HHHH (4 digits)

       \UHHHHHHHH
              Unicode character with hex value HHHHHHHH (8 digits)

       %%     a single %

       %b     ARGUMENT  as  a string with '\' escapes interpreted, except that
              octal escapes are of the form \0 or \0NNN

       %q     ARGUMENT is printed in a format that can be reused as shell  in‐
              put,  escaping  non-printable characters with the proposed POSIX
              $'' syntax.
        
       and all C format specifications ending with one of diouxXfeEgGcs,  with
       ARGUMENTs converted to proper type first.  Variable widths are handled.

       NOTE:  your shell may have its own version of printf, which usually su‐
       persedes the version described here.  Please refer to your shell's doc‐
       umentation for details about the options it supports.

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report    printf    translation    bugs   to   <https://translationpro‐
       ject.org/team/>

COPYRIGHT
       Copyright © 2018 Free Software Foundation, Inc.   License  GPLv3+:  GNU
       GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This  is  free  software:  you  are free to change and redistribute it.
       There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       printf(3)

       Full documentation at: <https://www.gnu.org/software/coreutils/printf>
       or available locally via: info '(coreutils) printf invocation'

GNU coreutils 8.30              September 2019                       PRINTF(1)
```

When you type q to exit, the below text appears on terminal, you will see :
```
--Man-- next: printf(3) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
```
You can press enter to continue to see another entry of printf.


**There are some useful man command options :**
* `-f option`
   
   Example :
   ```
   man -f printf
   ```
   It will display the short description of printf.
* `-k option`
   ```
   man -k printf
   ```
   It will search the short manual page descriptions for keywords and display any matches.
* `-w option`
   ```
   man -w printf
   ```
   It prints the location of cat files that will be displayed rather than the content of files.
* `-K option`
   ```
   man -K printf
   ```
   It will search for text in all manual pages.

### Manual Structure

|   Section   | Description                                                         |
| ----------- | ------------------------------------------------------------------- |
|   1         | General Commands                                                    |
|   2         | System Calls                                                        |
|   3	      | Library functions, covering in particular the C standard library    |
|   4 	      | Special files (usually devices, those found in /dev) and drivers    |
|   5	      | File formats and conventions                                        |
|   6	      | Games and screensavers                                              |
|   7	      | Miscellanea                                                         |
|   8	      | System administration commands and daemons                          |

### How to read the synopsis

These symbols are sometimes refered to as quotes.

The primary use of a man page is to lookup parameters for a program. Since most parameters are optional, they will be enclosed in square brackets.
```
[optional]
[-abcgln]
```

Some options will have a limited list of choices. A list of choices will be comma seperated and put between braces.
```
{choice1,choice2}
{yes,no}
```

Many sources of help documentation enclose manditory parameters between less-than/greater-than symbols.
```
<manditory>
<program_name>
```

## Vi Text Editor

The VI editor is the most popular and classic text editor in the Linux family. Below, are some reasons which make it a widely used editor :
1) It is available in almost all Linux Distributions
2) It works the same across different platforms and Distributions
3) It is user-friendly. Hence, millions of Linux users love it and use it for their editing needs

To launch the VI Editor -Open the Terminal (CLI) and type
```vim
vi <filename_NEW> or <filename_EXISTING>
```

**VI Editing commands**
```
    i - Insert at cursor (goes into insert mode)
    a - Write after cursor (goes into insert mode)
    A - Write at the end of line (goes into insert mode)
    ESC - Terminate insert mode
    u - Undo last change
    U - Undo all changes to the entire line
    o - Open a new line (goes into insert mode)
    dd - Delete line
    3dd - Delete 3 lines.
    D - Delete contents of line after the cursor
    C - Delete contents of a line after the cursor and insert new text. Press ESC key to end insertion.
    dw - Delete word
    4dw - Delete 4 words
    cw - Change word
    x - Delete character at the cursor
    r - Replace character
    R - Overwrite characters from cursor onward
    s - Substitute one character under cursor continue to insert
    S - Substitute entire line and begin to insert at the beginning of the line
    ~ - Change case of individual character
```
**Note** : You should be in the *"command mode"* to execute these commands. VI editor is case-sensitive so make sure you type the commands in the right letter-case. 

## Wildcards

Wildcards are symbols used in database searchs to represent a letter or letters in a word. It can be useful when searching for information because they enable different forms or spelling of a word to be searched similtaneously. 

### Basic set of wildcards

Here are some examples of wildcard characters for Access queries:

| Character | Description | Example|
| --------- | ----------- | ------ |
| *         | Matches any number of characters. You can use the asterisk (*) anywhere in a character string. |  wh* finds what, white, and why, but not awhile or watch. |
| ?         | Matches a single alphabet in a specific position. | b?ll finds ball, bell, and bill. |
| [ ]       | Matches characters within the brackets. | b[ae]ll finds ball and bell, but not bill. | 
| !         | Excludes characters inside the brackets. | b[!ae]ll finds bill and bull, but not ball or bell. Like “[!a]*” finds all items that do not begin with the letter a.
| -         | Matches a range of characters. Remember to specify the characters in ascending order (A to Z, not Z to A). | b[a-c]d finds bad, bbd, and bcd. |
| #         | Matches any single numeric character. | 1#3 finds 103, 113, and 123. |

### Example

For example, in Ebsohost databases: use ? to find one character only, or # to find one or more characters. For example:

```
wom?n --> will search for information containing the words woman or women
hum#r --> will search for information containing the words humor or humour.
```

## Permissions

Linux being a multi-user system uses permissions and ownership for security.

### Types of permissions

Every file and directory in your UNIX/Linux system has following 3 permissions defined for all the 3 owners discussed above.

- Read -->  This permission give you the authority to open and read a file. 
- Write -->  The write permission gives you the authority to modify the contents of a file. 
- Execute --> In Unix/Linux, you cannot run a program unless the execute permission is set. If the execute permission is not set, you might still be able to see/modify the program code(provided read & write permissions are set), but not run it.

### Permissions subjects

Every file and directory on your Unix/Linux system is assigned 3 types of owner, given below.

- user --> A user is the owner of the file. 
- group --> A user- group can contain multiple users. 
- other --> Any other user who has access to a file.  
----------------------------------
# **Bash Scripting**

BASH is an acronym for Bourne Again Shell. Shells are command interpreters. They are applications that provide users with the ability to give commands to their operating system interactively, or to execute batches of commands quickly. 

BASH is not an operating system or a window manager. It is also not our terminal (but it oftens runs inside your terminal). It does not control mouse or keyboard, does not configure your system, activate your screensaver, or open your files when we double-click them. It is generally not involved in launching applications from your window manager or desktop environment. It's important to understand that BASH is only an interface for you to execute statements (using BASH syntax), either at the interactive BASH prompt or via BASH scripts. 

## Variables

Variables are actually just one kind of parameter: parameters that are denoted by a name.

### Special variables

Here's a summary of most of the Special Parameters:

| Parameter Name | Usage    | Description |
| -------------- | -----    | ----------- |
| 0              | "$0"     | Contains the name, or the path, of the script. This is not always reliable. |
| 1 2 etc.       | "$1" etc.| Positional Parameters contain the arguments that were passed to the current script or function. |
| *              | "$*"     | Expands to all the words of all the positional parameters. Double quoted, it expands to a single string containing them all, separated by the first character of the IFS variable (discussed later). |
| @              | "$@"     | Expands to all the words of all the positional parameters. Double quoted, it expands to a list of them all as individual words. |
| #              | $#       | Expands to the number of positional parameters that are currently set. |
| ?              | $?       | Expands to the exit code of the most recently completed foreground command. |
| $              | $$       | Expands to the PID (process ID number) of the current shell. |
| !              | $!       | Expands to the PID of the command most recently executed in the background. |
| _             | "$_"      | Expands to the last argument of the last command that was executed. |

## Input

If we would like to ask the user for input then we use a command called read. This command takes the input and will save it into a variable.

```
read var
```

## Operations

There are description and examples for each of the arithmetic operators :

Operator  | Description  | Examples
------- | ------- | -------
| +  | Addition, measures addition of numbers (operands)  | $(( 10 + 3 )), result=13
| -  | Substraction, measures subtraction of second operand from first  | $(( 10 - 3 )), result=7
| *  | Multiplication, measures the multiplication of operands.  | $(( 10 * 3 )), result=30
| /  | Division, measures the division of first operand by second operand and and return quotient.  | $(( 10 / 3 )), result=3
| **  | Exponentiation, measures the result of second operand raised to the power of first operand.  | $((  10 ** 3 )), result=1000
| %  | Modulo, measures remainder when the first operand is divided by second operand.  | $(( 10 % 3 )), result=1
| +=  | Increment Variable by Constant- used to increment the value of first operand by the constant provided.  | x=10, let"x += 3", echo $x, result=13
| -=  | Decrement Variable by Constant- used to decrement the value of first operand by the constant provided.  | x=10, let "x -= 3", echo $x, result=7
| *=  | Multiply Variable by Constant- used to multiply the value of the first operand by the constant provided.  | x=10, let "x *= 3", echo $x, result=30
| /=  | Divide Variable by Constant- used to calculate the value of (variable / constant) and store the result back to variable.  | x=10, let "10 /= 3", echo $x, result=3 
| %=  | Remainder of Dividing Variable by Constant- used to calculate the value of (variable % constant) and store the result back to variable.  | x=10, let "10 %= 3", echo $x, result=1

### let

Syntax :
```md
let <arithmetic expression>  
```

Example :
```bash
#!/bin/bash  
      
x=10  
y=6  
z=0  
echo "Addition"  
let "z = $(( x + y ))"  
echo "z= $z"  
      
echo "Substraction"  
let "z = $((x - y ))"  
echo "z= $z"  
      
echo "Multiplication"  
let "z = $(( x * y ))"  
echo "z = $z"  
  
echo "Division"  
let "z = $(( x / y ))"  
echo "z = $z"  
  
echo "Exponentiation"  
let "z = $(( x ** y ))"  
echo "z = $z"  
  
echo "Modular Division"  
let "z = $(( x % y ))"  
echo "z = $z"  
  
let "x += 5"  
echo "Incrementing x by 5, then x= "  
echo $x  
  
let "x -= 5"  
echo "Decrementing x by 5, then x= "  
echo $x  
  
let "x *=5"  
echo "Multiply of x by 5, then x="  
echo $x  
  
let "x /= 5"  
echo "Dividing x by 5, x= "  
echo $x  
  
let "x %= 5"  
echo "Remainder of Dividing x by 5, x="  
echo $x  
```

### expr

Syntax
```
`expr item1 operator item2`  
or  
expr item1 operator item2  
```

Example :
```bash
#!/bin/bash  
#Basic arithmetic using expr  
  
echo "a=10, b=3"  
echo "c is the value of addition c=a+b"  
a=10  
b=3  
echo "c= `expr $a + $b`"  
```

### Double parentheses

Syntax
```
((expression))  
```

Example :
```bash
#!/bin/bash  
  
x=8  
y=2  
echo "x=8, y=2"  

echo "Addition of x & y"  
echo $(( $x + $y ))  

echo "Subtraction of x & y"  
echo $(( $x - $y ))  

echo "Multiplication of x & y"  
echo $(( $x * $y ))  

echo "Division of x by y"  
echo $(( $x / $y ))  

echo "Exponentiation of x,y"  
echo $(( $x ** $y ))  

echo "Modular Division of x,y"  
echo $(( $x % $y ))  

echo "Incrementing x by 5, then x= "  
(( x += 5 ))   
echo $x  

echo "Decrementing x by 5, then x= "  
(( x -= 5 ))  
echo $x  

echo "Multiply of x by 5, then x="  
(( x *= 5 ))  
echo $x  

echo "Dividing x by 5, x= "  
(( x /= 5 ))  
echo $x  

echo "Remainder of Dividing x by 5, x="  
(( x %= 5 ))  
echo $x  
```

### Length of a variable

Example :
```bash
myvar="some string"
echo ${#myvar}  
# 11
```

## Conditionals



### If statements

- if statement with the single condition. Example :
```bash
#!/bin/bash
echo "Enter a number"
read n
if [ $n -lt 100 ]; then
printf "$n is less than 100\n"
fi
```

- if statement with multiple conditions. Example :
```bash
#!/bin/bash
echo "Enter username"
read un
echo "Enter password"
read pw
if [[ "$un" == "admin" && "$pw" = "superuser" ]]; then
echo "Login Successful."
fi
```

*Use of if-else statement*

Syntax:
```bash
if [ condition ]; then
Command(s)
else
Command(s)
fi
```

- if-else statement with multiple conditions
```bash
#!/bin/bash
echo "Enter your name"
read name
if [[ $name == "Neha" || $name == 'Nil' ]]; then
echo "You have won the prize"
else
echo "Try for the next time"
fi
```

*Use of if-elif-else statement*

Syntax:
```bash
if [ condition ]; then
Command(s)
elif [ condition ]; then
Command(s)
…..
else
Command(s)
fi
```

- if-elif-else statement to check different conditions
```bash
#!/bin/bash
echo "Enter the mark"
read mark
if (( $mark >= 90 )); then
echo "Grade - A+"
elif (( $mark < 90 && $mark >= 80 )); then
echo "Grade - A"
elif (( $mark < 80 && $mark >= 70 )); then
echo "Grade - B+"
elif (( $mark < 70 && $mark >= 60 )); then
echo "Grade - C+"
else
echo "Grade - F"
fi
```

*Use of nested if*

Syntax:
```bash
if [ condition ]; then
Commands
if [ condition ]; then
Commands
fi
fi
```

### Case Statements

- case statement with a single value
```bash
#!/bin/bash
N1=$1
op=$2
N2=$3
case $op in
'+')
((Result=$N1+$N2)) ;;
'-')
((Result=$N1-$N2)) ;;
'x')
((Result=$N1*$N2)) ;;
'/')
((Result=$N1/$N2)) ;;
*)
echo "Wrong numbers of arguments"
exit 0 ;;
esac
echo "$N1 $op $N2 = $Result"
```

- case statement with a range of values
```bash
#!/bin/bash
#   Print grade based on the mark
name=$1
mark=$2
case $mark in
9[0-9]|100)
grade="A+" ;;
8[0-9])
grade="A" ;;
7[0-9])
grade="B+" ;;
6[0-9])
grade="C+" ;;
0|[0-9]|1[0-9]|2[0-9]|3[0-9]|4[0-9]|5[0-9])
grade="F" ;;
*)
echo "Invalid mark"
exit 0 ;;
esac
echo "$name obtained $grade"
```

### Test

Test is used by virtually every shell script written. It may not seem that way, because test is not often called directly. test is more frequently called as [.

### Boolean Operations

Operator  | Description  | Example
------- | ------- | -------
!  | This is logical negation. This inverts a true condition into false and vice versa.  | [ ! false ] is true.
-o  | This is logical OR. If one of the operands is true, then the condition becomes true.  | [ $a -lt 20 -o $b -gt 100 ] is true.
-a  | This is logical AND. If both the operands are true, then the condition becomes true otherwise false.  | [ $a -lt 20 -a $b -gt 100 ] is false. 

## Loops

Loops allow us to take a series of commands and keep re-running them until a particular situation is reached. They are useful for automating repetitive tasks.

### While loops

They have the following format :
```bash
while [ <some test> ]
do
<commands>
done
```

### Until loops

The until loop is fairly similar to the while loop. The difference is that it will execute the commands within it until the test becomes true.
```bash
until [ <some test> ]
do
<commands>
done
```

### For loops

It has the following syntax :
```bash
for var in <list>
do
<commands>
done
```

### Break and continue

The break statement tells Bash to leave the loop straight away, while The continue statement tells Bash to stop running through this iteration of the loop and begin the next iteration. 

### Select

The select mechanism allows you to create a simple menu system. 
```bash
select var in <list>
do
<commands>
done
```

## Funtions

A Bash function is essentially a set of commands that can be called numerous times. The purpose of a function is to help you make your bash scripts more readable and to avoid writing the same code repeatedly. 

It may be written in two different formats:
```bash
function_name () {
<commands>
}
```

or
```bash
function function_name {
<commands>
}
```

### Local variable

Global variables are variables that can be accessed from anywhere in the script regardless of the scope. In Bash, all variables by default are defined as global, even if declared inside the function.
```
note :
- When a local variable is set inside the function body with the same name as an existing global variable, it will have precedence over the global variable.
- Global variables can be changed from within the function.
```

### Overriding commands

It is possible to name a function as the same name as a command you would normally use on the command line. This allows us to create a wrapper. eg. Maybe every time we call the command ls in our script, what we actually want is ls -lh. 
