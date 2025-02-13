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