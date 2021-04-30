# Command Line

Command line is an interface that allows user to enter commands by typing its respective command. The
command line gives feedback outputs in the form of text. The reason for using the command line is that
the command line are more suitable for some taks than the GUI, such as data manipulation and file management.

## Table of Contents

- [Command Line and Shell](#command-line-and-shell)
- [Shell Command Structure](#shell-command-structure)
- [Basic Shell Commands](#basic-shell-commands)
- [Manual Pages](#manual-pages)
  - [Manual Structure](#manual-structure)
  - [How to read the synopsis](#how-to-read-the-synopsis)
- [Vi Text Editor](#vi-text-editor)
- [Wildcards](#wildcards)
  - [Basic set of wildcards](#basic-set-of-wildcards)
  - [Example](#example)
- [Permissions](#permissions)
  - [Types of permissions](#types-of-permissions)
  - [Permissions subjects](#permissions-subjects)

# Command Line and Shell

Shell is an environment in which we can run our commands, programs, and shell scripts. Whereas the
command line is the program we use to type in the commands we want to run in shell. In a nutshell,
A shell is a language in which we give the commands, and command line is the tool we use to send out these
commands. There are various shell available, and bash (bourne again shell) is the most commonly used.

# Shell Command Structure

- A shell command have a particular way in which they have to be written in.
- A shell command is case sensitive. command and Command is seen as different commands.
- Shell command structure: `command [options] [arguements]`
- Although, not all commands requires either options or arguements.

An arguement is the operand of a command. Just like operands to functions, some commands may be able to recieve multiple arguements. The structure of such command is as such: `command [arguements] [arguements] [arguements]`

An option is a modifier for a command which changes the way it is executed.
A dash(-) usually preceeds an option, and some commands may allow several options in one command. Some
options for some commands may have a short form (preceeded by a dash) and a long form (preceeded by
two dashes).
In short form, some option may be typed in this form: `command -[option][option][option]`
In long form, multiple options have to be typed in this manner: `command --[option] --[option] --[option]`

# Basic Shell Commands

1. cd
   Used to change directory.
   `cd [-L|-P] [DIRECTORY]` -> used to change the current directory to the given input
   Shortcuts:
   ~ -> shortcut to home directory
   . -> shortcut to current directory
   .. -> shortcut to upper directory
2. `pwd [OPTION]` -> Used to print the current working directory
3. `ls [OPTION]... [file]...` -> used to list the content of current directory
   -l -> used to give detailed information of the content of current directory
   -a -> used to list the contents of a directory, including hidden files
4. `mkdir [OPTION]... DIRECTORY...` -> Used to create a directory in the current directory
5. `rmdir [OPTION]... DIRECTORY...` -> Used to remove a directory in the current directory
6. `touch [OPTION]... FILE...` -> Used to create a blank file
7. `cp [OPTION]... SOURCE... DIRECTORY` -> used to copy a file or directory to the destination
8. `rm [OPTION]... [FILE]...` -> used to remove a file
9. `cat [OPTION]... [FILE]...` -> Used to concatenate files.
   
   `cat [filename1] [filename2]` -> used to show the contents from both of the file with the given
   filenames
   
   `cat >[filename]` -> used to create a file with the given 
   
   `cat [filename1] > [filename2]` -> used to copy the content from `[filename1]` to `[filename2]`
   
   `cat [filename1] >> [filename2]` -> used to append the contents of one file to the end of another file.
   
   `tac [filename]` -> used to display content in reverse order.

# Manual Pages

`man [command name]` -> used to look up the manual pages for a particular command

`man -k [keyword]` -> search the manual pages containing the given keyword

## Manual Structure

1. User commands
2. System calls
3. C library functions
4. Devices and special files
5. File formats and conventions
6. Games
7. Miscellaneous
8. System administration

A manual page of a command may consists of: name, synopsis, description, options, exit status, examples,
see also, environment, bugs, authors, history, and copyright.

## How to read the synopsis

- [] -> optional
- <> -> mandatory
- [  |  ] -> choose one
- ... -> allows multiple input

# Vi Text Editor

`vi [−rR] [−c command] [−t tagstring] [−w size] [file...]`
A command line text editor designed to overcome the limitations of the command line. Vi has two modes
of operations: command mode, which cause action to be taken on the file, and Insert mode in which
entered text is inserted into the file.
In the command mode, every character typed is a command that does something to the text file being edited;
a character typed in the command mode may even cause the vi editor to enter the insert mode. In the
insert mode, every character typed is added to the text in the file; pressing the <Esc> (Escape) key
turns off the Insert mode.

# Wildcards

Wildcards, also referred as globbing, are a set of building blocks that allow you to create a
pattern defining a set of files or directories.

## Basic set of wildcards

- \* -> represents zero or more characters
- ? -> represents a single character
- [] -> represents a range of characters (including)
- [\^] -> represents a range of characters (excluding)

## Example
```bash
cat *.txt
grep a=?
```

# Permissions

Dictates whether or not you are allowed to read, write, and execute a file.
The permissions for a file can be viewed by doing a long listing. It is structured as below.

```
-rwxrwxrwx
0123456789
```

0 -> identifies the file type; - for a normal file, d for a directory
1-3 -> represents the permissions for the owner
4-6 -> represents the permissions for the group
7-9 -> represents the permissions for other
Changing the permissions of a file can be done using the following command:
`chmod [permissions] [path]`

## Types of permissions

- r (read) -> allows the viewing of the contents of the file
- w (write) -> allows the changing of the contents of the file
- x (execute) -> allows the executing or running of the file (if it is a program or script)

## Permissions subjects

- owner - the singular owner of the file (usually also is the creator of the file)
- group - a single group to whom the file belongs
- others - everyone else who is not in the group or the owner
