# LINUX
1. Linux Kernel
   
The Linux kernel is the core of the Linux operating system. It acts as a bridge between hardware and software, managing system resources like CPU, memory, and input/output devices. The kernel handles:

Process management (allocating CPU time to applications)
Memory management (allocating RAM efficiently)
Device drivers (allowing software to communicate with hardware)
File system management (handling storage and files)

2. Linux Distribution (Distro)
A Linux distribution (distro) is a complete OS package that includes the Linux kernel, system utilities, libraries, and often a graphical user interface (GUI). Some popular Linux distros include:

Ubuntu (user-friendly, widely used)
Debian (stable, great for servers)
Fedora (cutting-edge features, backed by Red Hat)
Arch Linux (minimalist, for advanced users)
Kali Linux (focused on penetration testing and security)

3. Open Source

Linux is an open-source operating system, meaning its source code is freely available for anyone to view, modify, and distribute. Benefits of open-source software include:

Transparency (no hidden backdoors or spyware)
Customization (users can modify the code)
Community support (backed by global developers)
Security (frequent updates and patches)

4. CLI (Command-Line Interface) vs. GUI (Graphical User Interface)

* CLI (Command-Line Interface):
 
Uses text commands to interact with the system.
More powerful and efficient for advanced users.
Example: Terminal in Linux (e.g., ls, cd, grep).
* GUI (Graphical User Interface):
  
Uses icons, buttons, and windows for interaction.
Easier for beginners.
Examples: GNOME, KDE Plasma, Xfce.

# SHELL

The Linux environment allows the use of many different shells, some of which have been around for many years. The most commonly-used shell for Linux distributions is called the Bash shell. Bash provides many advanced features, such as command history and inline editing, which allows a user to easily re-execute previously executed commands or a variation of them via simple editing.

The Bash shell also has other popular features, a few of which are listed below:

1. Scripting: The ability to place commands in a file and then interpret (effectively use Bash to execute the contents of) the file, resulting in all of the commands being executed. This feature also has some programming features, such as conditional statements and the ability to create functions (AKA subroutines).
2. Aliases: The ability to create short nicknames for longer commands.
3. Variables: Used to store information for the Bash


# Commands
What is a command? The simplest answer is that a command is a software program that, when executed on the CLI, performs an action on the computer.

To execute a command, the first step is to type the name of the command. Click in the terminal on the right. Type ls and hit Enter. The result should resemble the example below:

Many commands can be used by themselves with no further input. Some commands require additional input to run correctly. This additional input comes in two forms: options and arguments.

The typical format for a command is as follows:

command [options] [arguments]

# arguments

command [options] [arguments]
An argument can be used to specify something for the command to act upon. If the ls command is given the name of a directory as an argument, it lists the contents of that directory. In the following example, the /etc/ppp directory is used as an argument; the resulting output is a list of files contained in that directory:

sysadmin@localhost:~$ ls /etc/ppp                                 
ip-down.d  ip-up.d                                                
The ls command also accepts multiple arguments. To list the contents of both the /etc/ppp and /etc/ssh directories, pass them both as arguments:

sysadmin@localhost:~$ ls /etc/ppp /etc/ssh         
/etc/ppp:                       
ip-down.d  ip-up.d                                  
/etc/ssh:                                                         
moduli               ssh_host_dsa_key.pub     ssh_host_rsa_key      sshd_configssh_config
ssh_host_ecdsa_key   ssh_host_rsa_key.pub         
ssh_host_dsa_key     ssh_host_ecdsa_key.pub 

# options

command [options] [arguments]
Options can be used with commands to expand or modify the way a command behaves. For example, using the -l option of the ls command results in a long listing, providing additional information about the files that are listed, such as the permissions, the size of the file and other information:

sysadmin@localhost:~$ ls -l                                       
total 0
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Desktop             
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Documents           
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Downloads           
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Music               
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Pictures            
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Public               
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13 Templates           
drwxr-xr-x 1 sysadmin sysadmin 0 Jan 29  20:13

Note that, in the command above, -l is a lowercase letter "L". An easy way to remember this is -l is a mnemonic (easy to memorize programming code) for long listing).

# HISTORY

When a command is executed in the terminal, it is stored in a history list. This is designed to make it easy to execute the same command, later eliminating the need to retype the entire command.

Pressing the Up Arrow ↑ key displays the previous command on the prompt line. The entire history of commands run in the current session can be displayed by pressing Up repeatedly to move back through the history of commands that have been run. Pressing the Enter key runs the displayed command again.

When the desired command is located, the Left Arrow ← and Right Arrow → keys can position the cursor for editing. Other useful keys for editing include the Home, End, Backspace and Delete keys.

To view the history list of a terminal, use the history command:

If the desired command is in the list that the history command generates, it can be executed by typing an exclamation point ! character and then the number next to the command

If the history command is passed a number as an argument, it outputs that number of previous commands from the history list. For example, to show the last three commands:

sysadmin@localhost:~$ history 3
    6  date                                                                     
    7  ls /home                                                                   
    8  history 3

    To execute the most recent command type !! and hit Enter:

    To execute the most recent iteration of a specific command, type ! followed by the name of the command and hit Enter. For example, to execute the most recent ls command

 
 # VARIABLES

 Variables
A variable is a feature that allows the user or the shell to store data. This data can be used to provide critical system information or to change the behavior of how the Bash shell (or other commands) work. Variables are given names and stored temporarily in memory. There are two types of variables used in the Bash shell: local and environment.

**Local Variables

Local Variables
Local or shell variables exist only in the current shell, and cannot affect other commands or applications. When the user closes a terminal window or shell, all of the variables are lost. They are often associated with user-based tasks and are lowercase by convention.

To set the value of a variable, use the following assignment expression. If the variable already exists, the value of the variable is modified. If the variable name does not already exist, the shell creates a new local variable and sets the value:

variable=value

The following example creates a local variable named variable1 and assigns it a value of Something:

sysadmin@localhost:~$ variable1='Something'

The echo command is used to display output in the terminal. To display the value of the variable, use a dollar sign $ character followed by the variable name as an argument to the echo command:

sysadmin@localhost:~$ echo $variable1                                   
Something

The echo command is used to display output in the terminal. To display the value of the variable, use a dollar sign $ character followed by the variable name as an argument to the echo command:

sysadmin@localhost:~$ echo $variable1                                   
Something

# ENVIRONMENT VARIABLES

 Environment Variables
Environment variables, also called global variables, are available system-wide, in all shells used by Bash when interpreting commands and performing tasks. The system automatically recreates environment variables when a new shell is opened. Examples include the PATH, HOME, and HISTSIZE variables. The HISTSIZE variable defines how many previous commands to store in the history list. The command in the example below displays the value of the HISTSIZE variable:

To modify the value of an existing variable, use the assignment expression:

sysadmin@localhost:~$ HISTSIZE=500                                            
sysadmin@localhost:~$ echo $HISTSIZE                              
500  

When run without arguments, the env command outputs a list of the environment variables. Because the output of the env command can be quite long, the following examples use a text search to filter that output.

In a previous example variable1 was created as a local variable, so the following search in the environment variables results in no output:

sysadmin@localhost:~$ env | grep variable1                              
The pipe | character passes the output of the env command to the grep command, which searches the output.

This text filtering technique will be covered in detail later in the course.

The export command is used to turn a local variable into an environment variable.

export variable
After exporting variable1, it is now an environment variable. It is now found in the search through the environment variables:

sysadmin@localhost:~$ export variable1                                  
sysadmin@localhost:~$ env | grep variable1
variable1=Something
The export command can also be used to make a variable an environment variable upon its creation by using the assignment expression as the argument:

sysadmin@localhost:~$ export variable2='Else'                           
sysadmin@localhost:~$ env | grep variable2                             
variable2=Else
To change the value of an environment variable, use the assignment expression:

sysadmin@localhost:~$ variable1=$variable1' '$variable2                
sysadmin@localhost:~$ echo $variable1                                   
Something Else
Exported variables can be removed using the unset command:

sysadmin@localhost:~$ unset variable2

# COMMAND TYPES

Command Types
One way to learn more about a command is to look at where it comes from. The type command can be used to determine information about command type.

type command

# INTERNAL COMMANDS

Internal Commands
Also called built-in commands, internal commands are built into the shell itself. A good example is the cd (change directory) command as it is part of the Bash shell. When a user types the cd command, the Bash shell is already executing and knows how to interpret it, requiring no additional programs to be started.

The type command identifies the cd command as an internal command:


# Aliases

An alias can be used to map longer commands to shorter key sequences. When the shell sees an alias being executed, it substitutes the longer sequence before proceeding to interpret commands.


New aliases can be created using the following format, where name is the name to be given the alias and command is the command to be executed when the alias is run.

alias name=command

For example, the cal 2019 command displays the calendar for the year 2019. Suppose you end up running this command often. Instead of executing the full command each time, you can create an alias called mycal and run the alias, as demonstrated in the following graphic:


sysadmin@localhost:~$ alias mycal="cal 2019"                                    
sysadmin@localhost:~$ mycal

# FUNCTIONS

Functions
Functions can also be built using existing commands to either create new commands, or to override commands built-in to the shell or commands stored in files. Aliases and functions are normally loaded from the initialization files when the shell first starts.

Functions are more advanced than aliases and typically are used in Bash shell scripts. Typically, functions are used to execute multiple commands. To create a function, the following syntax is used:

    function_name () 
{
   commands
}

In the format above, function_name can be anything that the administrator wants to call the function. The commands that the administrator wants to execute can replace the commands placeholder. Note the formatting, in particular, the location of the parenthesis () and braces {}, as well as the convention of using tabs to make the function more easily readable.

Functions are useful as they allow for a set of commands to be executed one at a time instead of typing each command repeatedly

In the example below, a function called my_report is created to execute the ls, date, and echo commands.

sysadmin@localhost:~$ my_report () {                                            
> ls Documents                                                                  
> date                                                                          
> echo "Document directory report"                                              
> } 
>
> # QUOTING

 Quoting
Quotation marks are used throughout Linux administration and most computer programming languages to let the system know that the information contained within the quotation marks should either be ignored or treated in a way that is very different than it would normally be treated. There are three types of quotes that have special significance to the Bash shell: double quotes ", single quotes ', and back quotes `. Each set of quotes alerts the shell not to treat the text within the quotes in the normal way.

# Double Quotes
Double quotes stop the shell from interpreting some metacharacters (special characters), including glob characters.

Within double quotes an asterisk is just an asterisk, a question mark is just a question mark, and so on, which is useful when you want to display something on the screen that is normally a special character to the shell. In the echo command below, the Bash shell doesn't convert the glob pattern into filenames that match the pattern:

# Single Quotes
Single quotes prevent the shell from doing any interpreting of special characters, including globs, variables, command substitution and other metacharacters that have not been discussed yet.

# Backquotes
Backquotes, or backticks, are used to specify a command within a command, a process called command substitution. This allows for powerful and sophisticated use of commands.


1.  To begin, note the output of the date command:

sysadmin@localhost:~$ date                                           
Mon Nov  4 03:35:50 UTC 2018

2. Now, note the output of the echo command:

sysadmin@localhost:~$ echo Today is date                               
Today is date

3. In the previous command, the word date is treated as regular text, and the shell passes date to the echo command. To execute the date command and have the output of that command sent to the echo command, put the date command in between two backquote characters:

sysadmin@localhost:~$ echo Today is `date`                         
Today is Mon Nov 4 03:40:04 UTC 2018

# CONTROL STATEMENTS
Control statements allow you to use multiple commands at once or run additional commands, depending on the success of a previous command. Typically these control statements are used within scripts, but they can also be used on the command line as well.

# SEMICOLON

command1; command2; command3

The semicolon ; character can be used to run multiple commands, one after the other. Each command runs independently and consecutively; regardless of the result of the first command, the second command runs once the first has completed, then the third and so on.

For example, to print the months of January, February and March of 2030, execute the following command:

    sysadmin@localhost:~$ cal 1 2030; cal 2 2030; cal 3 2030               

# DOUBLE AMPERSAND
Double Ampersand

command1 && command2

The double ampersand && acts as a logical "and"; if the first command is successful, then the second command will also run. If the first command fails, then the second command will not run.

# DOUBLE PIPE

Double Pipe
command1 || command2
The double pipe || is a logical "or". Depending on the result of the first command, the second command will either run or be skipped.

With the double pipe, if the first command runs successfully, the second command is skipped; if the first command fails, then the second command is run. In other words, you are essentially telling the shell, "Either run this first command or the second one”.

# Getting Help

# Man Pages
UNIX is the operating system that Linux was modeled after. The developers of UNIX created help documents called man pages (short for manual pages).

Man pages are used to describe the features of commands. They provide a basic description of the purpose of the command, as well as details regarding available options.

To view a man page for a command, use the man command:

man command
For example, the following displays the man page for the ls command:

sysadmin@localhost:~$ man ls

To exit viewing a man page, use the Q key.

# Searching Man Pages

To search a man page for a term, type the / character followed by a search term, then hit the Enter key. The program searches from the current location down towards the bottom of the page to try to locate and highlight the term.

# Man Pages Categorized by Sections

Until now, we have been displaying man pages for commands. However, there are several different types of commands (user commands, system commands, and administration commands), configuration files and other features, such as libraries and kernel components, that require documentation.

As a result, there are thousands of man pages on a typical Linux distribution. To organize all of these man pages, they are categorized by sections.

By default, there are nine sections of man pages:

General Commands
System Calls
Library Calls
Special Files
File Formats and Conventions
Games
Miscellaneous
System Administration Commands
Kernel Routines

The man command searches each of these sections in order until it finds the first match. For example, if you execute the command man cal, the first section (General Commands) is searched for a man page called cal. If not found, then the second section is searched. If no man page is found after searching all sections, an error message is returned:

To determine which section a specific man page belongs to, look at the numeric value on the first line of the output of the man page. For example, the cal command belongs to the first section of man pages:

#  Finding Commands and Documentation
The whatis command (or man -f) returns what section a man page is stored in. This command occasionally returns unusual output, such as the following:

#Where Are These Commands Located?
To search for the location of a command or the man pages for a command, use the whereis command. This command searches for commands, source files and man pages in specific locations where these files are typically stored:

# Find Any File or Directory
The whereis command is specifically designed to find commands and man pages. While this is useful, it is often necessary to find a file or directory, not just files that are commands or man pages.

To find any file or directory, use the locate command. This command searches a database of all files and directories that were on the system when the database was created. Typically, the command to generate this database is run nightly.

Any files created today will not be searchable with the locate command. If root access is available, it’s possible to update the locate database manually by running the updatedb command. Regular users cannot update the database file.

# Using the Help Option
Many commands will provide basic information, very similar to the SYNOPSIS found in man pages, by simply using the --help option to the command. This option is useful to learn the basic usage of a command quickly without leaving the command line:

# NAVIGATING THE FILE System

Like Windows, the Linux directory structure, typically called a filesystem, also has a top level. However instead of My Computer, it is called the root directory, and it is symbolized by the slash / character. Additionally, there are no drives in Linux; each physical device is accessible under a directory, as opposed to a drive letter.

The following image shows a visual representation of a typical Linux filesystem:

# Home Directory
The term home directory often confuses new Linux users. To begin with, on most Linux distributions there is a directory called home under the root / directory.

Under this /home directory there is a directory for each user on the system. The directory name is the same as the name of the user, so a user named sysadmin would have a home directory called /home/sysadmin.

# Recursive Listing
There are times when you want to display all of the files in a directory as well as all of the files in all subdirectories under that directory. This is called a recursive listing.

To perform a recursive listing, use the -R option to the ls command:

sysadmin@localhost:~$ ls -R /etc/ppp
/etc/ppp:
ip-down.d  ip-up.d         

/etc/ppp/ip-down.d:
bind9

/etc/ppp/ip-up.d:
bind9

Note that in the previous example, the files in the /etc/ppp directory were listed first. After that, the contents of its subdirectories /etc/ppp/ip-down.d and /etc/ppp/ip-up.d were listed.

#  Sort a Listing
By default, the ls command sorts files alphabetically by file name. Sometimes, it may be useful to sort files using different criteria.

To sort files by size, we can use the -S option. Note the difference in the output of the following two commands. The same files and directories are listed, but in a different order:

While the -S option works by itself, it is most useful when used with the -l option so the file sizes are visible. The following command lists files from largest to smallest and displays the actual size of the file.

# The following command will list files by modification date, oldest to newest:

sysadmin@localhost:~$ ls -lrt /etc/ssh                                 
total 580
-rw-r--r-- 1 root root   3264 Feb 10  2018 sshd_config
-rw-r--r-- 1 root root   1580 Feb 10  2018 ssh_config
-rw-r--r-- 1 root root 553122 Feb 10  2018 moduli
-rw-r--r-- 1 root root    338 Jul 19 06:52 ssh_import_id
-rw-r--r-- 1 root root    399 Jul 19 06:52 ssh_host_rsa_key.pub
-rw------- 1 root root   1679 Jul 19 06:52 ssh_host_rsa_key
-rw-r--r-- 1 root root     99 Jul 19 06:52 ssh_host_ed25519_key.pub
-rw------- 1 root root    411 Jul 19 06:52 ssh_host_ed25519_key
-rw-r--r-- 1 root root    179 Jul 19 06:52 ssh_host_ecdsa_key.pub
-rw------- 1 root root    227 Jul 19 06:52 ssh_h


# MANAGING FILES AND directories

It is important to note that everything in Linux is case-sensitive, a feature carried over from Unix. This means that the shell recognizes a lowercase a-z character as completely different from an uppercase A-Z character. When manipulating files, pay attention to your capitalization: a hello.txt file is different from HELLO.txt and Hello.txt files.

# GLOBBING 

Globbing
Glob characters are often referred to as wild cards. These are symbol characters that have special meaning to the shell.

**  Asterisk * Character
The asterisk * character is used to represent zero or more of any character in a filename. For example, to display all of the files in the /etc directory that begin with the letter t:

sysadmin@localhost:~$ echo /etc/t*                              
/etc/terminfo /etc/timezone /etc/tmpfiles.d

You can use the asterisk character at any place within the filename pattern. For example, the following matches any filename in the /etc directory that ends with .d:

sysadmin@localhost:~$ echo /etc/*.d                                 
/etc/apparmor.d /etc/binfmt.d /etc/cron.d /etc/depmod.d /e

In the next example, all of the files in the /etc directory that begin with the letter r and end with .conf are displayed:

sysadmin@localhost:~$ echo /etc/r*.conf                             
/etc/resolv.conf /etc/rsyslog.conf

# Question Mark ? Character
The question mark ? character represents any single character. Each question mark character matches exactly one character, no more and no less.

Suppose you want to display all of the files in the /etc directory that begin with the letter t and have exactly 7 characters after the t character:

sysadmin@localhost:~$ echo /etc/t???????      
/etc/terminfo /etc/timezone

Glob characters can be used together to find even more complex patterns. The pattern /etc/*???????????????????? command only matches files in the /etc directory with twenty or more characters in the filename:

sysadmin@localhost:~$ echo /etc/*????????????????????            
/etc/bindresvport.blacklist /etc/ca-certificates.con

The asterisk and question mark could also be used together to look for files with three-letter extensions by using the /etc/*.??? pattern:

sysadmin@localhost:~$ echo /etc/*.???                
/etc/issue.net /etc/locale.gen

# Bracket [ ] Characters
The bracket [] characters are used to match a single character by representing a range of characters that are possible match characters. For example, the /etc/[gu]* pattern matches any file that begins with either a g or u character and contains zero or more additional characters:

sysadmin@localhost:~$ echo /etc/[gu]*                              
/etc/gai.conf /etc/groff /etc/group /etc/group- /etc/gshadow /etc/gshadow- /etc/
gss /etc/ucf.conf /etc/udev /etc/ufw /etc/update-motd.d /etc/updatedb.conf      

Brackets can also be used to a represent a range of characters. For example, the /etc/[a-d]* pattern matches all files that begin with any letter between and including a and d:

sysadmin@localhost:~$ echo /etc/[a-d]*
/etc/adduser.conf /etc/alternatives /etc/apparmor /et


The /etc/*[0-9]* pattern displays any file that contains at least one number:

sysadmin@localhost:~$ echo /etc/*[0-9]*                            
/etc/X11 /etc/dbus-1 /etc/iproute2 /etc/mke2fs.conf /e

#  Exclamation Point ! Character
The exclamation point ! character is used in conjunction with the square brackets to negate a range. For example, the pattern /etc/[!DP]* matches any file that does not begin with a D or P.

# Listing With Globs

There is a simple solution to this problem: always use the -d option with globs, which tells the ls command to display the name of directories, instead of their contents:

sysadmin@localhost:~$ls -d /etc/x*                                             
/etc/xdg

# Copying Files
The cp command is used to copy files. It requires a source and a destination. The structure of the command is as follows:

cp source destination

The source is the file to be copied. The destination is where the copy is to be located. When successful, the cp command does not have any output (no news is good news). The following command copies the /etc/hosts file to your home directory:

sysadmin@localhost:~$ cp /etc/hosts ~                                     
sysadmin@localhost:~$ ls
Desktop    Downloads  Pictures  Templates  hosts                          
Documents  Music      Public    Videos          

Reminder: The ~ character represents your home directory.

#  Verbose Mode
The -v option causes the cp command to produce output if successful. The -v option stands for verbose:

sysadmin@localhost:~$ cp -v /etc/hosts ~                              
`/etc/hosts' -> `/home/sysadmin/hosts'

# Avoid Overwriting Data
The cp command can be destructive to existing data if the destination file already exists. In the case where the destination file exists, the cp command overwrites the existing file's contents with the contents of the source file.

To answer n to each prompt automatically, use the -n option. It stands for no clobber, or no overwrite.

# Copying Directories
By default, the cp command will not copy directories; any attempt to do so results in an error message:


However, the recursive -r option allows the cp command to copy both files and directories.

cp -r source_directory destination_directory


Be careful with this option. The entire directory structure will be copied which could result in copying a lot of files and directories!

NOTE : 

Consider This

The options -r and -R serve the same purpose. However, -R can be used with most commands, while -r can have different meanings with some commands. For example, while cp -r means copy recursively (both files and directories), ls -r means reverse sort.

# Moving Files
To move a file, use the mv command. The syntax for the mv command is much like the cp command:

mv source destination

In the following example, the hosts file that was generated previously is moved from the current directory to the Videos directory:

sysadmin@localhost:~$ ls                                               
Desktop    Downloads  Pictures  Templates  example.txt  hosts.copy     
Documents  Music      Public    Videos     hosts                       
sysadmin@localhost:~$ mv hosts Videos                                  
sysadmin@localhost:~$ ls                                               
Desktop    Downloads  Pictures  Templates  example.txt                 
Documents  Music      Public    Videos     hosts.copy                 
sysadmin@localhost:~$ ls Videos                                        
hosts   

When a file is moved, the file is removed from the original location and placed in a new location. Moving files can be somewhat tricky in Linux because users need specific permissions to remove files from a directory. Without the right permissions, a Permission denied error message is returned:

# Renaming Files
The mv command is not just used to move a file, but also to rename a file. If the destination for the mv command is a directory, the file is moved to the directory specified. The name of the file only changes if a destination file name is also specified.

sysadmin@localhost:~$ ls                                               
Desktop    Downloads  Pictures  Templates  example.txt                          
Documents  Music      Public    Videos     hosts.copy                 
sysadmin@localhost:~$ mv example.txt Videos/newexample.txt             
sysadmin@localhost:~$ ls
Desktop    Downloads  Pictures  Templates  hosts.copy                           
Documents  Music      Public    Videos                               
sysadmin@localhost:~$ ls Videos                                       
hosts  newexample.txt                                                  
If a destination directory is not specified, the file is renamed using the destination file name and remains in the source directory. For example, the following commands renames the newexample.txt file to myfile.txt:

# Additional Move Options
Like the cp command, the mv command provides the following options:

‌⁠​​⁠​
Option	Meaning
-i	Interactive: Ask if a file is to be overwritten.
-n	No Clobber: Do not overwrite a destination file's contents.
-v	Verbose: Show the resulting move.
Important

There is no -r option as the mv command moves directories by default.

# Creating Files

To create an empty file, use the touch command as demonstrated below:

#  Removing Files
To delete a file, use the rm command:

Warning

The files are permanently deleted. There is no command to undelete a file and no trash can from which to recover deleted files.

As a precaution, users should use the -i option when deleting multiple files:

# Removing Directories
You can delete directories using the rm command. However, the default behavior (no options) of the rm command is to not delete directories:

sysadmin@localhost:~$ rm Videos                                        
rm: cannot remove `Videos': Is a directory 

To delete a directory with the rm command, use the -r recursive option:

When a user deletes a directory, all of the files and subdirectories are deleted without any interactive question. It is best to use the -i option with the rm command.

# Creating Directories
To create a directory, use the mkdir command:


# ARCHIVING AND COMPRENSION

File archiving is used when one or more files need to be transmitted or stored as efficiently as possible. There are two fundamental aspects which this chapter explores:

Archiving: Combines multiple files into one, which eliminates the overhead in individual files and makes the files easier to transmit.
Compression: Makes the files smaller by removing redundant information.

Benefits of archiving :
    When making a large number of files available, such as the source code to an application or a collection of documents, it is easier for people to download a compressed archive than it is to download files individually.

    Log files have a habit of filling disks, so it is helpful to split them by date and compress older versions.
    When backing up directories, it is easier to keep them all in one archive than it is to version (update) each file.

    Some streaming devices such as tapes perform better if you’re sending a stream of data rather than individual files.

    It can often be faster to compress a file before sending it to a tape drive or over a slower network and decompress it at the other end than it would be to send it uncompressed.

    Linux provides several tools to compress files; the most common is gzip. Here we show a file before and after compression:

    sysadmin@localhost:~$ cd Documents
sysadmin@localhost:~/Documents$ ls -l longfile*
-rw-r--r-- 1 sysadmin sysadmin 66540 Dec 20  2017 longfile.txt
sysadmin@localhost:~/Documents$ gzip longfile.txt
sysadmin@localhost:~/Documents$ ls -l longfile*
-rw-r--r-- 1 sysadmin sysadmin 341 Dec 20  2017 longfile.txt.gz

In the preceding example, there is a file called longfile.txt that is 66540 bytes. The file is compressed by invoking the gzip command with the name of the file as the only argument. After that command completes, the original file is gone, and a compressed version with a file extension of .gz is left in its place. The file size is now 341 bytes.

The gzip command will provide this information, by using the –l option, as shown here:

sysadmin@localhost:~/Documents$ gzip -l longfile.txt.gz
         compressed        uncompressed  ratio uncompressed_name
                341               66540  99.5% lo

Compressed files can be restored to their original form using either the gunzip command or the gzip –d command. This process is called decompression. After gunzip does its work, the longfile.txt file is restored to its original size and file name.

There are other commands that operate virtually identically to gzip and gunzip. These include bzip2 and bunzip2, as well as xz and unxz

# ARCHIVING

If you had several files to send to someone, you could choose to compress each one individually. You would have a smaller amount of data in total than if you sent uncompressed files, however, you would still have to deal with many files at one time.

Archiving is the solution to this problem. The traditional UNIX utility to archive files is called tar, which is a short form of TApe aRchive. It was used to stream many files to a tape for backups or file transfer. The tar command takes in several files and creates a single output file that can be split up again into the original files on the other end of the transmission.

The tar command has three modes that are helpful to become familiar with:

Create: Make a new archive out of a series of files.
Extract: Pull one or more files out of an archive.
List: Show the contents of the archive without extracting.


** CREATE MODE **

 Create Mode
tar -c [-f ARCHIVE] [OPTIONS] [FILE...]
Creating an archive with the tar command requires two named options:

Option	Function
-c	Create an archive.
-f ARCHIVE	
Use archive file.

The argument ARCHIVE will be the name of the resulting archive file.

All the remaining arguments are considered as input file names, either as a wildcard, a list of files, or both.

The following example shows a tar file, also called a tarball, being created from multiple files. The first argument creates an archive called alpha_files.tar. The wildcard option * is used to include all files that begin with alpha in the archive:

    sysadmin@localhost:~/Documents$ tar -cf alpha_files.tar alpha*
    sysadmin@localhost:~/Documents$ ls -l alpha_files.tar
    -rw-rw-r-- 1 sysadmin sysadmin 10240 Oct 31 17:07 alpha_files.tar

The final size of alpha_files.tar is 10240 bytes. Normally, tarball files are slightly larger than the combined input files due to the overhead information on recreating the original files. Tarballs can be compressed for easier transport, either by using gzip on the archive or by having tar do it with the -z option.

Option	Function
-z	Compress (or decompress) an archive using the gzip command.

The next example shows the same command as the prior example, but with the addition of the -z option.

sysadmin@localhost:~/Documents$ tar -czf alpha_files.tar.gz alpha*
sysadmin@localhost:~/Documents$ ls -l alpha_files.tar.gz
-rw-rw-r-- 1 sysadmin sysadmin 417 Oct 31 17:15 alpha_files.tar.gz

The output is much smaller than the tarball itself, and the resulting file is compatible with gzip, which can be used to view the compression details. The uncompressed file is the same size as it would be if you tarred it in a separate step:

    sysadmin@localhost:~/Documents$ gzip -l alpha_files.tar.gz
         compressed        uncompressed  ratio uncompressed_name
                417               10240  96.1% alpha_files.tar


** List Mode **

tar -t [-f ARCHIVE] [OPTIONS]
Given a tar archive, compressed or not, you can see what’s in it by using the -t option. The next example uses three options:

Option	Function
-t	List the files in an archive.
-j	Decompress with an bzip2 command.
-f ARCHIVE	Operate on the given archive.

To list the contents of the folders.tbz archive:

sysadmin@localhost:~/Documents$ tar -tjf folders.tbz
School/
School/Engineering/
School/Engineering/hello.sh
School/Art/
School/Art/linux.txt
School/Math/
School/Math/numbers.txt

# Extract Mode

tar -x [-f ARCHIVE] [OPTIONS]
Creating archives is often used to make multiple files easier to move. Before extracting the files, relocate them to the Downloads directory:

    sysadmin@localhost:~/Documents$ cd ~
    sysadmin@localhost:~$ cp Documents/folders.tbz Downloads/folders.tbz
    sysadmin@localhost:~$ cd Downloads

Finally, you can extract the archive with the –x option once it’s copied into a different directory. The following example uses a similar pattern as before, specifying the operation, the compression, and a file name to operate on.


Option	Function
-x	Extract files from an archive.
-j	Decompress with the bzip2 command.
-f ARCHIVE	Operate on the given archive.

sysadmin@localhost:~/Downloads$ tar -xjf folders.tbz
sysadmin@localhost:~/Downloads$ ls -l
total 8
drwx------ 5 sysadmin sysadmin 4096 Dec 20  2017 School
-rw-rw-r-- 1 sysadmin sysadmin  413 Oct 31 18:37 folders.tbz

The original file is untouched, and the new directory is created. Inside the directory, are the original directories and files.

sysadmin@localhost:~/Downloads$ cd School
sysadmin@localhost:~/Downloads/School$ ls -l
total 12
drwx------ 2 sysadmin sysadmin 4096 Oct 31 17:45 Art
drwx------ 2 sysadmin sysadmin 4096 Oct 31 17:47 Engineering
drwx------ 2 sysadmin sysadmin 4096 Oct 31 17:46 Math

Add the –v flag and you will get a verbose output of the files processed, making it easier to keep track of what's happening:

Option	Function
-v	Verbosely list the files processed.

The next example repeats the prior example, but with the addition of the –v option:

sysadmin@localhost:~/Downloads$ tar -xjvf folders.tbz
School/
School/Engineering/
School/Engineering/hello.sh
School/Art/
School/Art/linux.txt
School/Math/
School/Math/numbers.txt

# ZIP Files
The de facto archiving utility in Microsoft is the ZIP file. ZIP is not as prevalent in Linux but is well supported by the zip and unzip commands. Albeit, with tar and gzip/gunzip the same commands and options can be used interchangeably to do the creation and extraction, but this is not the case with zip. The same option has different meanings for the two different commands.

The default mode of zip is to add files to an archive and compress it.

zip [OPTIONS] [zipfile [file…]]
The first argument zipfile is the name of the archive to be created, after that, a list of files to be added. The following example shows a compressed archive called alpha_files.zip being created:

sysadmin@localhost:~/Documents$ zip alpha_files.zip alpha*
  adding: alpha-first.txt (deflated 32%)
  adding: alpha-second.txt (deflated 36%)
  adding: alpha-third.txt (deflated 48%)
  adding: alpha.txt (deflated 53%)
  adding: alpha_files.tar.gz (stored 0%)

  The output shows the files and the compression ratio.

It should be noted that tar requires the –f option to indicate a filename is being passed, while zip and unzip require a filename and therefore don’t need you to inform the command a filename is being passed.

The zip command will not recurse into subdirectories by default, which is different behavior than the tar command. That is, merely adding School will only add the empty directory and not the files under it. If you want tar like behavior, you must use the –r option to indicate recursion is to be used:

sysadmin@localhost:~/Documents$ zip -r School.zip School
updating: School/ (stored 0%)
updating: School/Engineering/ (stored 0%)
updating: School/Engineering/hello.sh (deflated 88%)
updating: School/Art/ (stored 0%)
updating: School/Art/linux.txt (deflated 49%)
updating: School/Math/ (stored 0%)
updating: School/Math/numbers.txt (stored 0%)
  adding: School/Art/red.txt (deflated 33%)
  adding: School/Art/hidden.txt (deflated 1%)
  adding: School/Art/animals.txt (deflated 2%)

In the example above, all files under the School directory are added because it uses the –r option. The first lines of output indicate that directories were added to the archive, but otherwise the output is similar to the previous example.

The –l list option of the unzip command lists files in .zip archives:

sysadmin@localhost:~/Documents$ unzip -l School.zip
Archive:  School.zip
  Length      Date    Time    Name
---------  ---------- -----   ----
        0  2017-12-20 16:46   School/
        0  2018-10-31 17:47   School/Engineering/
      647  2018-10-31 17:47   School/Engineering/hello.sh
        0  2018-10-31 19:31   School/Art/
       83  2018-10-31 17:45   School/Art/linux.txt
        0  2018-10-31 17:46   School/Math/
       10  2018-10-31 17:46   School/Math/numbers.txt
       51  2018-10-31 19:31   School/Art/red.txt
       67  2018-10-31 19:30   School/Art/hidden.txt
       42  2018-10-31 19:31   School/Art/animals.txt
---------                     -------
      900                     10 files
        0  2018-10-31 17:46   School/Math/
       10  2018-10-31 17:46   School/Math/numbers.txt
---------                     -------
      740                     7 files 

# WORKING WITH text

 **  Viewing Files in the Terminal **

. One of the most popular uses of cat is to display the content of text files. To display a file in the standard output using the cat command, type the command followed by the filename:

sysadmin@localhost:~$ cd Documents
sysadmin@localhost:~/Documents$ cat food.txt 
Food is good.


Although the terminal is the default output of this command, the cat command can also be used for redirecting file content to other files or input for another command by using redirection characters.

 # Viewing Files Using a Pager
While viewing small files with the cat command poses no problems, it is not an ideal choice for large files. The cat command doesn't provide any easy ways to pause and restart the display, so the entire file contents are dumped to the screen.

For larger files, use a pager command to view the contents. Pager commands display one page of data at a time, allowing you to move forward and backward in the file by using movement keys.

There are two commonly used pager commands:

The less command provides a very advanced paging capability. It is usually the default pager used by commands like the man command.
The more command has been around since the early days of UNIX. While it has fewer features than the less command, however, the less command isn't included with all Linux distributions. The more command is always available.

# Pager Movement Commands
To view a file with the less command, pass the file name as an argument:

sysadmin@localhost:~/Documents$ less words

The first group of movement commands to focus on are the ones that are most commonly used. To make it even more convenient, the keys that are identical in more and less are summarized below in order to demonstrate how to move in more and less at the same time:

‌⁠​​⁠​ 
Key	Movement
Spacebar	Window forward
B	        Window backward
Enter	    Line forward
Q	        Exit
H	        Help

# Pager Searching Commands
There are two ways to search in the less command: searching forward or backward from your current position.

To start a search to look forward from your current position, use the slash / key. Then, type the text or pattern to match and press the Enter key.

Abdul
Abdul's
Abe
/frog
If a match can be found, then the cursor moves in the document to the match. For example, in the following graphic the expression "frog" was searched for in the words file:

bullfrog
bullfrog's
bullfrogs
bullheaded
bullhorn
bullhorn's
Notice that "frog" didn't have to be a word by itself. Also notice that while the less command moved to the first match from the current position, all matches were highlighted.

If no matches forward from your current position can be found, then the last line of the screen will report Pattern not found:

Pattern not found (press RETURN)

# Head and Tail
The head and tail commands are used to display only the first few or last few lines of a file, respectively (or, when used with a pipe, the output of a previous command). By default, the head and tail commands display ten lines of the file that is provided as an argument.

Passing a number as an option will cause both the head and tail commands to output the specified number of lines, instead of the standard ten. For example to display the last five lines of the /etc/sysctl.conf file use the -5 option:

# Command Line Pipes
The pipe | character can be used to send the output of one command to another. Typically, when a command has output or generates an error, the output is displayed to the screen; however, this does not have to be the case. Instead of being printed to the screen, the output of one command becomes input for the next command. This tool can be powerful, especially when looking for specific data; piping is often used to refine the results of an initial command.

The following example displays only the first ten lines:

sysadmin@localhost:~$ ls /etc | head
X11
adduser.conf
alternatives
apparmor
apparmor.d
apt
bash.bashrc
bind
bindresvport.blacklist
binfmt.d

It is important to carefully choose the order in which commands are piped, as each command only sees input from the previous command. The examples below illustrate this using the nl command, which adds line numbers to the output. In the first example, the nl command is used to number the lines of the output of the preceding ls command:

sysadmin@localhost:~$ ls /etc/ssh | nl
     1  moduli
     2  ssh_config
     3  ssh_host_ecdsa_key
     4  ssh_host_ecdsa_key.pub
     5  ssh_host_ed25519_key
     6  ssh_host_ed25519_key.pub
     7  ssh_host_rsa_key
     8  ssh_host_rsa_key.pub
     9  ssh_import_id
    10  sshd_config
In the next example, note that the ls command is executed first and its output is sent to the nl command, numbering all of the lines from the output of the ls command. Then the tail command is executed, displaying the last five lines from the output of the nl command:

sysadmin@localhost:~$ ls /etc/ssh | nl | tail -5
     6  ssh_host_ed25519_key.pub
     7  ssh_host_rsa_key
     8  ssh_host_rsa_key.pub
     9  ssh_import_id
    10  sshd_config
Compare the output above with the next example:

sysadmin@localhost:~$ ls /etc/ssh | tail -5 | nl
     1  ssh_host_ed25519_key.pub
     2  ssh_host_rsa_key
     3  ssh_host_rsa_key.pub
     4  ssh_import_id
     5  sshd_config
Notice how the line numbers are different. Why is this?

In the second example, the output of the ls command is first sent to the tail command which only grabs the last five lines of the output. Then the tail command sends those five lines to the nl command, which numbers them 1-5.

#  STDOUT
STDOUT can be directed to files. To begin, observe the output of the following echo command which displays to the screen:

sysadmin@localhost:~$ echo "Line 1"
Line 1
Using the > character, the output can be redirected to a file instead:

sysadmin@localhost:~$ echo "Line 1" > example.txt
This command displays no output because STDOUT was sent to the file example.txt instead of the screen. You can see the new file with the output of the ls command.

sysadmin@localhost:~$ ls
Desktop    Downloads  Pictures  Templates  example.txt
Documents  Music      Public    Videos   
The file contains the output of the echo command, which can be viewed with the cat command:

sysadmin@localhost:~$ cat example.txt                                  
Line 1
It is important to realize that the single arrow overwrites any contents of an existing file:

sysadmin@localhost:~$ cat example.txt
Line 1
sysadmin@localhost:~$ echo "New line 1" > example.txt
sysadmin@localhost:~$ cat example.txt
New line 1
The original contents of the file are gone, replaced with the output of the new echo command.

It is also possible to preserve the contents of an existing file by appending to it. Use two arrow >> characters to append to a file instead of overwriting it:

sysadmin@localhost:~$ cat example.txt
New line 1
sysadmin@localhost:~$ echo "Another line" >> example.txt
sysadmin@localhost:~$ cat example.txt
New line 1
Another line
Instead of being overwritten, the output of the echo command is added to the bottom of the file.

#  Sorting Files or Input
The sort command can be used to rearrange the lines of files or input in either dictionary or numeric order

# Viewing File Statistics
The wc command provides the number of lines, words and bytes (1 byte = 1 character in a text file) for a file, and a total line count if more than one file is specified. By default, the wc command allows for up to three statistics to be printed for each file provided, as well as the total of these statistics if more than one filename is provided:


# BASIC SCRIPTING 

Shell Scripts in a Nutshell
A shell script is a file of executable commands that has been stored in a text file. When the file is run, each command is executed. Shell scripts have access to all the commands of the shell, including logic. A script can therefore test for the presence of a file or look for particular output and change its behavior accordingly. You can build scripts to automate repetitive parts of your work, which frees your time and ensures consistency each time you use the script. For instance, if you run the same five commands every day, you can turn them into a shell script that reduces your work to one command.

A script can be as simple as one command:

echo "Hello, World!"

# Scripting Basics

You got your first taste of scripting earlier in this chapter where we introduced a very basic script that ran a single command. The script started with the shebang (or hashbang) line, telling Linux that /bin/bash (which is Bash) is to be used to execute the script.

Other than running commands, there are 3 topics you must become familiar with:

1.Variables, which hold temporary information in the script
2.Conditionals, which let you do different things based on tests you write
3.Loops, which let you do the same thing over and over

Linux scripting involves writing a series of commands in a file to automate tasks, reduce repetitive work, and enhance system efficiency. The most common type of scripting in Linux is Bash scripting

# 2. Variables in Bash
Variables store data that can be reused in the script.

bash
Copy
Edit
#!/bin/bash
name="John"
echo "Hello, $name!"
Variables are assigned without spaces.
Use $variable to access the value.


#  Conditional Statements
If-Else Condition
bash
Copy
Edit
#!/bin/bash
echo "Enter a number:"
read num

if [ $num -gt 10 ]; then
    echo "Number is greater than 10"
else
    echo "Number is 10 or less"
fi
-gt means greater than, other comparisons include:
-lt (less than)
-eq (equal to)
-ne (not equal to)
-ge (greater than or equal to)
-le (less than or equal to )

#  Loops in Bash
1.For Loop

#!/bin/bash
for i in {1..5}
do
    echo "Iteration $i"
done

2.While Loop

#!/bin/bash
counter=1
while [ $counter -le 5 ]
do
    echo "Count: $counter"
    ((counter++))
done


# Functions in Bash

#!/bin/bash
greet() {
    echo "Hello, $1!"
}

greet "Alice"
greet "Bob"

Functions allow code reuse.
$1 is the first argument passed to the function.

# LOG FILES


Log files are useful for many reasons; they help troubleshoot problems and determine whether or not unauthorized access has been attempted.

Some processes can log their own data to these files, other processes rely on a separate process (a daemon) to handle these log data files.

In yet more recent distributions, those based on systemd, the logging daemon is named journald, and the logs are designed to allow for mainly text output, but also binary. The standard method for viewing journald-based logs is to use the journalctl command.

Regardless of what the daemon process being used, the log files themselves are almost always placed into the /var/log directory structure. Although some of the file names may vary, here are some of the more common files to be found in this directory:

File	Contents
1.boot.log	Messages generated as services are started during the startup of the system.

2.cron	Messages generated by the crond daemon for jobs to be executed on a recurring basis.

3.dmesg	Messages generated by the kernel during system boot up.

4.maillog	Messages produced by the mail daemon for e-mail messages sent or received.

5.messages	Messages from the kernel and other processes that don't belong elsewhere. Sometimes named syslog instead of messages after the daemon that writes this file.

6.secure	Messages from processes that required authorization or authentication (such as the login process).

7.journal	Messages from the default configuration of the systemd-journald.service; can be configured in the /etc/journald.conf file amongst other places.

8.Xorg.0.log	Messages from the X Windows (GUI) server.

# NETWORK configuration

The ifconfig command stands for interface configuration and is used to display network configuration information. 

# The ip Command
The ifconfig command is becoming obsolete in some Linux distributions (deprecated) and is being replaced with a form of the ip command, specifically ip addr show.

The ip command differs from ifconfig in several important manners, chiefly that through its increased functionality and set of options, it can almost be a one-stop shop for configuration and control of a system’s networking. The format for the ip command is as follows:

ip [OPTIONS] OBJECT COMMAND

# The route Command
Recall that a router (or gateway) is a machine that allows hosts from one network to communicate with another network. To view a table that describes where network packages are sent, use the route command:

root@localhost:~# route                                             
Kernel IP routing table                                             
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface   
192.168.1.0     *               255.255.255.0   U     0      0        0 eth0  
default         192.168.1.1     0.0.0.0        UG     0      0        0 eth0 
The first highlighted line in the preceding example indicates that any network packet sent to a machine in the 192.168.0 network is not sent to a gateway machine (the * indicates no gateway). The second highlighted line indicates that all other network packets are sent to the host with the IP address of 192.168.1.1 (the router).

# The ping Command
The ping command can be used to determine if another machine is reachable. If the ping command can send a network package to another machine and receive a response, then you should be able to connect to that machine.

By default, the ping command continues sending packages endlessly. To limit how many pings to send, use the -c option followed by a number indicating how many iterations you desire. The following examples show ping being limited to 4 iterations.

It is important to note that just because the ping command fails does not mean that the remote system is unreachable. Some administrators configure their machines (and even entire networks!) to not respond to ping requests because a server can be attacked by something called a denial of service attack. In this sort of attack, a server is overwhelmed by a massive number of network packets. By ignoring ping requests, the server is less vulnerable.

As a result, the ping command may be useful for checking the availability of local machines, but not always for machines outside of your own network.

#  The netstat Command
The netstat command is a powerful tool that provides a large amount of network information. 

For example, to display statistics regarding network traffic, use the -i option to the netstat command:

To use the netstat command to display routing information, use the -r option:

# The dig Command
There may be times when you need to test the functionality of the DNS server that your host is using. One way of doing this is to use the dig command, which performs queries on the DNS server to determine if the information needed is available on the server.

# The host Command
In its simplest form, the host command works with DNS to associate a hostname with an IP address. As used in a previous example, example.com is associated with the IP address of 192.168.1.2:

root@localhost:~# host example.com                                            
example.com has address 192.168.1.2                                           
The host command can also be used in reverse if an IP address is known, but the domain name is not.

root@localhost:~# host 192.168.1.2                                            
2.1.168.192.in-addr.arpa domain name pointer example.com.                     
2.1.168.192.in-addr.arpa domain name pointer cserver.example.com.      

# The ssh Command
The ssh command allows you to connect to another machine across the network, log in and then perform tasks on the remote machine.

If you only provide a machine name or IP address to log into, the ssh command assumes you want to log in using the same username that you are currently logged in as. To use a different username, use the syntax:

username@hostname
root@localhost:~# ssh bob@test
The authenticity of host ‘test (127.0.0.1)’ can’t be established.
RSA key fingerprint is c2:0d:ff:27:4c:f8:69:a9:c6:3e:13:da:2f:47:e4:c9.
Are you sure you want to continue connection (yes/no)? yes
Warning: Permanently added ‘test’ (RSA) to the list of known hosts.
bob@test’s password:
bob@test:~$ date
Fri Oct   4 16:14:43 CDT 2013                                            
To return back to the local machine, use the exit command:

bob@test:~$ exit
logout
Connection to test closed.
root@localhost:~#


#  Switching Users
The su command allows you to run a shell as a different user. While switching to the root user is what the su command is used for most frequently, it can also switch to other users as well.

su [options] [username]

After using the shell started by the su command to perform the necessary administrative tasks, return to your original shell (and original user account) by using the exit command.

#  Executing Privileged Commands
The sudo command allows users to execute commands as another user. Similar to the su command, the root user is assumed by default.

sudo [options] command

Using the sudo command to execute an administrative command results in an entry placed in a log file. Each entry includes the name of the user who executed the command, the command that was executed and the date and time of execution. This allows for increased accountability, compared to a system where many users might know the root password and can either log in directly as root or use the su command to execute commands as the root user.

One big advantage of using sudo to execute administrative commands is that it reduces the risk of a user accidentally executing a command as root. The intention to execute a command is clear; the command is executed as root if prefixed with the sudo command. Otherwise, the command is executed as a regular 

# USER MANAGEMENT 

To access the root user account, the su or sudo commands are normally used.

The su command is usually used to switch users and start a new shell as another user, with the default being the root user. The su command is often used when a series of commands need to be executed as the root user.

The sudo command is typically used to execute a single command as the root user by prefixing that command with sudo. The sudo command must be configured by the root user before an ordinary user can use it. By default, the sudo command stays in effect for 15 minutes on Ubuntu systems where the root account is not enabled by default. Root access has been enabled on the virtual machine used in this lab allowing the su command to be used.

By default on many Ubuntu systems, sudo commands entered after the first sudo command will be executed as root without being prompted for a password for the next 15 minutes. Other systems may have different timeouts.

Use the grep command to view the record for your sysadmin account:

grep sysadmin /etc/passwd

By using the grep command, the output only includes the account information for that one username.

# Passwords
The /etc/shadow file contains information about users’ passwords. In this exercise you will use several commands to view the data in this file.


  # Creating A Group
The groupadd command can be executed by the root user to create a new group. The command requires only the name of the group to be created. The -g option can be used to specify a group id for the new group:


#  Modifying a Group
The groupmod command can be used to either change the name of a group with the -n option or change the GID for the group with the -g option.

# Consider This

These files with no group name are called orphaned files. To search for all files that are owned by just a GID (not associated with a group name) use the -nogroup option of the find command:

# DELETING A GROUP 

As long as the group to be deleted is not a user's primary group, deleting the group is accomplished by using the groupdel command along with the name of the group:

# Creating a User
Once you've verified which default values to use and you've gathered the information about the user, then you are ready to create a user account. An example of a useradd command using a few options looks like the following:


root@localhost:~# useradd -u 1009 -g users -G sales,research -m -c 'Jane Doe' jane 


This example of the useradd command creates a user with a UID of 1009, a primary group of users, supplementary memberships in the sales and research groups, a comment of "Jane Doe", and an account name of jane.

After executing the previous command, the information about the jane user account is automatically added to the /etc/passwd and /etc/shadow files, while the information about supplemental group access is automatically added to the /etc/group and /etc/gshadow files:

# Setting a User Password
There are several ways for a user password to be changed. The user can execute the passwd command, the administrator can execute the passwd command providing the username as an argument, or graphical tools are also available.

The administrator can use the passwd command to either set the initial password or change the password for the account. For example, if the administrator had created the account jane, then executing passwd jane provides the administrator a prompt to set the password for the jane account. If completed successfully, then the /etc/shadow file will be updated with the user's new password.

# Deleting a User
The userdel command is used to delete users. When you delete a user account, you also need to decide whether to delete the user's home directory. The user's files may be important to the organization, and there may even be legal requirements to keep the data for a certain amount of time, so be careful not to make this decision lightly. Also, unless you've made backup copies of the data, once you've executed the command to delete the user and their files, there is no reversing the action.

To delete the user jane without deleting the user's home directory /home/jane, execute:

root@localhost:~# userdel jane
Beware that deleting a user without deleting their home directory means that the user's home directory files will be orphaned and these files will be owned solely by their former UID and GID.

To delete the user, home directory, and mail spool as well, use the -r option:

root@localhost:~# userdel -r jane

# SUMMARY

Create a new group with the groupadd command
Make changes to groups using the groupmod command
Create a new user with the useradd command
Set and reset a user's password with the passwd command
Make changes to the user account with the usermod command

# NOTE

Use the groupmod command with the -n option to change the name of the sales group.

Now use the groupmod command with the -g option to change the GID for the group.

# File ownership can be confirmed using the long listing -l option of the ls command. Use this command to view the contents of the new directories:

ls -l priv-dir
ls -l pub-dir
Your output should contain the following:

sysadmin@localhost:/tmp$ ls -l priv-dir                                   
total 0                                                                         
-rw-rw-r-- 1 sysadmin sysadmin 0 Feb 24 18:20 priv-file                   
sysadmin@localhost:/tmp$ ls -l pub-dir                                    
total 0                                                                         
-rw-rw-r-- 1 sysadmin sysadmin 0 Feb 24 18:20 pub-file                    
sysadmin@localhost:/tmp$
Notice that for each file listed, the first character of the line is the hyphen, -. This conveys the information that the items are regular files. The first character of the listing indicates the type of file. These file types are listed in the table below:

Character	Meaning
d	indicates a directory
-	is a regular file
l	is a symbolic link
b	is a block device file
c	is a character device file
p	is a pipe file
s	is a socket file
The next nine characters are in three groups of three characters.

The first group of three characters is the user owner's permissions:

-rw-rw-r-- 1 sysadmin sysadmin 0 Apr 11 21:27 pub-file 
The next three characters are the group owner's permissions:

-rw-rw-r-- 1 sysadmin sysadmin 0 Apr 11 21:27 pub-file
The last three characters represent everyone else's permissions (referred to as "others"):

-rw-rw-r-- 1 sysadmin sysadmin 0 Apr 11 21:27 pub-file
When viewing permissions, r indicates the read permission, w indicates the write permission and x indicates execute permission. A - character indicates that that permission has not been granted.

Following the permissions is a link count number, indicating how many files are linked to this file. Next, you see the user owner, the group owner, the size of the file, the date/time the file was last modified and the file name.

# MAKING A DIRECTORY PRIVATE

If you want to make a directory more private use the chmod command to remove permissions that others have on the directory. Using the -d option with the ls command will list directory entries instead of contents.

Use the ls -ld command to view permissions for the priv-dir directory, then use the chmod command to remove the others' permissions for read and execute:

ls -ld priv-dir/
chmod o-rx priv-dir/
sysadmin@localhost:/tmp$ ls -ld priv-dir/                                 
drwxrwxr-x 2 sysadmin sysadmin 4096 Feb 24 18:20 priv-dir/                
sysadmin@localhost:/tmp$ chmod o-rx priv-dir/
Finally, use the same ls command to verify the change in permissions. The output now shows that others have no permission or access to the priv-dir directory:

ls -ld priv-dir/
sysadmin@localhost:/tmp$ ls -ld priv-dir/                                 
drwxrwx--- 2 sysadmin sysadmin 23 Feb 24 18:20 priv-dir/                
sysadmin@localhost:/tmp$
You can use the chmod command to modify the permissions for others by using an o character followed by either a + character or a - character to add or subtract permissions. The = character can be used to set an exact permission.

You could also use a u character instead of an o character to modify the permissions of the user owner. Use a g character if you want to change permissions for the group owner. This method of changing permissions is referred to as symbolic since it uses letters to represent permission groups. The u, g, o or user, group, others notation may be easier to use than the octal method which relies on a binary translation of an octal (base 8) number:

To modify everyone's permissions use an a character instead of o, u or g.

Examples:

chmod a+x file	Gives everyone execute permission
chmod g-w file	Removes write permission for group owners
chmod go+r file	Adds read permission for group owner and others
chmod o=rwx	Sets others permissions to read, write and execute

# MAKING A DIRECTORY Public

If you want to make a directory more public, then you can use the chmod command to add write permission for others:

ls -ld pub-dir/
chmod o+w pub-dir/
ls -ld pub-dir/
Your output now shows that others have write permission on the directory (the ability to add or delete files inside the directory):

sysadmin@localhost:/tmp$ ls -ld pub-dir/                                  
drwxrwxr-x 2 sysadmin sysadmin 22 Feb 24 18:20 pub-dir/                 
sysadmin@localhost:/tmp$ chmod o+w pub-dir/                               
sysadmin@localhost:/tmp$ ls -ld pub-dir/                                 
drwxrwxrwx 2 sysadmin sysadmin 22 Feb 24 18:20 pub-dir/               
sysadmin@localhost:/tmp$

# Removing permissions from the group

Use the chmod command to remove any permission from the group and others on the priv-file:

ls -l priv-dir/priv-file
chmod g-rw,o-r priv-dir/priv-file
ls -l priv-dir/priv-file

# Grant all users the same read and write permission for the pub-file:

ls -l pub-dir/pub-file
chmod a=rw pub-dir/pub-file
ls -l pub-dir/pub-file

# File ownership

There are two commands that can affect the ownership of files: the chown command and the chgrp command. The chown command can only be executed by the root user and it can change both the user and group that owns a file.

The chgrp command can be used by either the user who owns a file or by the root user.

The chgrp command only changes the group that owns a file.

When a non-root user uses the chgrp command, they can only change the group ownership to a group of which they are a member. The root user can use chgrp to change the group ownership of any file to any group.

# FILE permissions

Setuid
When the setuid permission is set on an executable binary file (a program) the binary file is run as the owner of the file, not as the user who executed it. This permission is set on a handful of system utilities so that they can be run by normal users, but executed with the permissions of root, providing access to system files that the normal user doesn't normally have access to.

Like the read, write and execute permissions, special permissions can be set with the chmod command, using either the symbolic and octal methods.

To add the setuid permission symbolically, run:

chmod u+s file
To add the setuid permission numerically, add 4000 to the file's existing permissions (assume the file originally had 775 for its permission in the following example):

chmod 4775 file
To remove the setuid permission symbolically, run:

chmod u-s file
To remove the setuid permission numerically, subtract 4000 from the file's existing permissions:

chmod 0775 file
Previously, we set permission with the octal method using three-digit codes. When a three-digit code is provided, the chmod command assumes that the first digit before the three-digit code is 0. Only when four digits are specified is a special permission set.

If three digits are specified when changing the permission on a file that already has a special permission set, the first digit will be set to 0, and the special permission will be removed from the file.

#  Setgid
The setgid permission is similar to setuid, but it makes use of the group owner permissions. There are two forms of setgid permissions: setgid on a file and setgid on a directory. The behavior of setgid depends on whether it is set on a file or directory.

#  Setgid on Files
The setgid permission on a file is very similar to setuid; it allows a user to run an executable binary file in a manner that provides them additional (temporary) group access. The system allows the user running the command to effectively belong to the group that owns the file, but only in the setgid program.

A good example of the setgid permission on an executable file is the

# Setgid on Directories
When set on a directory, the setgid permission causes files created in the directory to be owned by the group that owns the directory automatically. This behavior is contrary to how new file group ownership would normally function, as by default new files are group owned by the primary group of the user who created the file.

# Setting Setgid
Use the following syntax to add the setgid permission symbolically:

chmod g+s <file|directory>
To add the setgid permission numerically, add 2000 to the file's existing permissions (assume in the following example that the directory originally had 775 for its permissions):

chmod 2775 <file|directory>
To remove the setgid permission symbolically, run:

chmod g-s <file|directory>
To remove the setgid permission numerically, subtract 2000 from the file's existing permissions:

chmod 0775 <file|directory>

# Sticky Bit
The sticky bit permission is used to prevent other users from deleting files that they do not own in a shared directory. Recall that any user with write permission on a directory can create files in that directory, as well as delete any file in the directory, even if they do not own the file!

To set the sticky bit permission symbolically, execute a command like the following:

chmod o+t <directory>
To set the sticky bit permission numerically, add 1000 to the directory's existing permissions (assume the directory in the following example originally had 775 for its permissions):

chmod 1775 <file|directory>
To remove the sticky permission symbolically, run:

chmod o-t <directory>
‌⁠​​⁠​To remove the sticky bit permission numerically, subtract 1000 from the directory's existing permissions:

chmod 0775 <directory>

# LISTING DIRECTORY information

Using the -d option for the ls command lists directory information; combined with the -l option it shows ownership and permissions for the directory files. List the details of the /tmp and /var/tmp directories:

ls -ld /tmp
ls -ld /var/tmp
The output shows the permissions on these directories to be the same:

sysadmin@localhost:~$ ls -ld /tmp                                         
drwxrwxrwt 1 root root 4096 Feb 24 20:19 /tmp                                   
sysadmin@localhost:~$ ls -ld /var/tmp                                     
drwxrwxrwt 2 root root 4096 Jan 18  2021 /var/tmp                         
sysadmin@localhost:~$
The /tmp and /var/tmp directories are read, write and executable for everyone. Besides the users' home directories, these two "temporary" directories are the locations in the filesystem where ordinary users can create new files or directories.

This does pose a problem: if all users can create new files, they are also able to delete existing files. This is because the write permission on a directory grants users the ability to add and delete files in a directory.

The t in the execute column for the others permissions indicates that this directory has the sticky bit permission set. This special permission means that even though everyone can add files in these directories, only the user who creates a file can delete that file.

The root user is not affected by this permission as that account can delete all files in the directory, regardless of ownership.

# Hard and Soft Links

