# linux command line cheat sheet
open terminal: ctrl+Alt+t
open current location in the explorers in ubuntu terminal: xdg-open .
<br>
necessary commands after installation:
to install some necessary tools: sudo apt install gimp gparted synaptic <br>
undo all unnecessary security: sudo apt install ubuntu-restricted-extras
<hr>

# mostly used Options :  
```
-E : causes less to automatically exit the first time it reaches end of file. 
-f : forces non-regular file to open. 
-F : causes less to exit if entire file can be displayed on first screen 
-g : highlight the string which was found by last search command 
-G : suppresses all highlighting of strings found by search commands 
-i : cause searches to ignore case 
-n : suppresses line numbers 
-p : pattern : it tells less to start at the first occurrence of pattern in the file 
-s : causes consecutive blank lines to be squeezed into a single blank line 
```

# usefull more options:
```
~                               : home dir
example:
cd ~                            : will change dir to home dir

/                               : root dir
```

#   Bash Commands:
```
short note:
1. uname -a                    :Show system and kernel
                               : '-a'--> show all 
                               : 'uname'--> user name 
run command: uname -a


2. head -n1 /etc/issue         :Show distribution


3. mount                       :Show mounted filesystems
4. date                        :Show system date
5. uptime                      : Show uptime

6. whoami                      :Show your username
7. man <command>               :Show manual/ details for command
run command: man date          
```
# Bash Shortcuts

```
CTRL-c                          :Stop current command
CTRL-z                          :Sleep program
CTRL-a                          :Go to start of line
CTRL-e                          :Go to end of line
CTRL-u                          :Cut from start of line
CTRL-k                          :Cut to end of line
CTRL-r                          :Search history
see: https://www.youtube.com/watch?v=H0tUtzx2xX8&t=150s

!!                              :Repeat last command
!abc                            :Run last command starting with abc
!abc:p                          :Print last command starting with abc
!$                              :Last argument of previous command
!*                              :All arguments of previous command
^abc^123                        :Run previous command, replacing abcwith 123

```

# Bash Variables:
```
env                             :Show environment variables
echo $NAME                      :Output value of $NAME variable
                                : it is like a print function
example: a=2
         echo $a                : will show the output '2'
export NAME =value              :Set $NAME to value

use of '-e'                     : converts the '\' and '\n'
example: 
echo -e 'some \text\n xyz'      : out put: some 	ext
                                             xyz



$PATH                           :Executable search path
$HOME                           :Home directory
$SHELL                          :Current shell
```


# cat command
### use command to know about cat: man cat
```
cat                             : command use and in next line we can write and at another next line it will print
                                : we can write till stop (ctrl+d)                                 
```
<img src="pictures/car print.png"/>
<br>

```
cat text.txt                    : show text inside the text.txt file
cat text.txt text2.txt          : will show 2 files contents togater one after another

cat -n text.txt                 : will add line number to each line cause of '-n' option
cat -s text.txt                 : will decreases more than one empty lines to one line cause of '-s' option
```

# IO Redirection
### use command to know about: man <command>
### '<' or  '>' are the directions
```
command < file                  : Read input of command from file
example 
1: cat < file.txt               : file.txt will be read and show
example 2: 
head -n 7 < file.txt            : print first 7 lines from file.txt

command > file                  :Write output of command to file
example: cat > file.txt         
        1
        2
        3
        4 
('ctrl+ d' to stom input)         : 1,2,3,4 digits will be overrided in the file.txt

command >> file                   :Append output to file, won't over write
example: cat >> file.txt

cat text1.txt text2.txt > out.txt : will concatinate the content of two files and output to an out.txt file

command > /dev/null               :Discard output of command
example: 
head file.txt > /dev/null         : will read the file.txt but won't show anything



command1 | command2               :Pipe output of command1 to command2
example:
cat file.txt | head -7 | tail -5  
```

# ls commands / Directory Operations
### use command to know about ls: man ls
```
man ls                              : show how we can use ls    
ls                                  : List of files
                                    : LS COMMAND ALSO USES 2ND AND 3RD PARAMETERS
ls [options] [directory]            :
examples:
1. ls Document/                     : show list of files in the Documents
2. ls -l                            : with all info show list of files (details)
3. ls -a                            : with all the hidden files show list of files
4. ls -al                           : will show long list os all hidden and not hidden files
5. ls -lS                           : sort by size and show long list
6. ls Documents/*.html              : show for all html files in documents
7. ls -lS > Documents/out.txt       : write in file, sort by size and show long list
                                    : here in the Documents/out.txt file we will have a output
                                    : in stead of shoing in terminal
8. cd 'new folder'                  : will change directory to 'new folder' 
9. ls -d */                         : list of only the dir
10. cd dir                          : Change directory to dir
11. cd ..                           : Go up a directory
12. cd ..\..                        : go two step back
13 cd /                             : go to root directory
14. cd                              : home directory
```

# Directory Operations
### use command to know about the command: man <command>
```                                 
pwd                                 :(Print Working Directory) Show current directory
mkdir dir                           :Make directory dir

```

# ls Options
```
-a                      :Show all (including hidden)
example: ls -a
example2: ls -al        : two option togater

-R                      :Recursive list
-r                      :Reverse order
-t                      :Sort by last modified
-S                      :Sort by file size
-l                      :Long listing format
-1                      :One file per line
-m                      :Comma-separated output
-Q                      :Quoted output
```


# Search Files:
```
grep: Global regular expression print (pattern match and print)

1. grep <pattern> <files>               :Search for pattern in files (Case sensitive)
example: 
grep "OPTIONS" out.txt                  : will find all the lines which contain 'out.txt'
example 2:
grep -n "OPTIONS" out.txt               : will find all the lines which contain 'out.txt' and print the line numvers

2. grep -i                              :by using '-i': Case insensitive search (Case insensitive)
3. grep -r                              :Recursive search
4. grep -v                              :Inverted search
                                        :The –v option tells grep to invert its output, meaning that instead of printing matching lines, do the opposite and print all of the lines that don’t match the expression.


5. find /dir/ -name name*                               :Find files starting with name in dir
example: 
command: pwd
output : /home/user/Downloads
command: find /home/user/Downloads/ -name data*         : find the file which's name stars with data
output : /home/user/Downloads/data.txt
command :find /home/user/Downloads/ -name *.txt         : will find all the files, has .txt at end 



6. find /dir/ -user name                                :Find files owned by name in dir

7. find /dir/ -mtime -1                                 : find all the file that created 1 day ago

8. find /dir/ -mmin num                                 :Find files modifed less than num minutes ago in dir
9. whereis command                                      :Find binary / source / manual for command
        whereis [options] filename
        example: whereis dir


10. locate file                                         :Find file (quick search of system index)
for locate file(if not warking): sudo apt install mlocate 
example of use: locate -i school*note   : locate a file that name cotain school and note words

```

# File Operations
```
1. touch file1                                     :Create file1
2. cat file1 file2                                 :Concatenate files and output
3. less file1                                      :View and paginate file1
                                                    :For example, if it’s a large file and you are reading it using any text editor, then the complete file will be loaded to main memory. The less command doesn’t load the entire file, but loads it part by part which makes it faster.

4. file file1                                          :Get type of file1
5. cp file1 file2                                      :Copy file1 to file2
6. mv file1 file2                                      :Move file1 to file2
7. rm file1                                            :Delete file1
8. head file1                                          :Show first 10 lines of file1
9. tail file1                                          :Show last 10 lines of file1
10. tail -f file1                                      :Output last lines of file1 as it changes
```

# Process Management
```
ps                                      :Show snapshot of processes
top                                     :Show real time processes
kill pid                                :Kill process with id pid
pkill name                              : Kill process with name name
killall name                            :Kill all processes with names beginning name
```

# Nano Shortcuts
Using Nano Text Editor Commands in Linux
GNU nano is a popular command-line text editor that is included in most Linux distributions. The interface is comparable to GUI-based text editors, which makes nano a popular choice for those who find vi or emacs commands non-intuitive. This guide shows you how to use Nano Text Editor Commands in Linux.
see: https://www.linode.com/docs/guides/use-nano-text-editor-commands/

### to start nano shell: just type 'nano' in the terminal

```
Files:

Ctrl+R Read file
Ctrl+O Save file
Ctrl+X Close file

Cut and Paste:
ALT+A Start marking text
CTRL+K Cut marked text or line
CTRL+U Paste text

Navigate File:
ALT+/ End of file
CTRL+A Beginning of line
CTRL+E End of line
CTRL+C Show line number
CTRL+_ Go to line number

Search File
CTRL+W Find
ALT+W Find next
CTRL+\ Search and replace

```



# Screen Shortcuts
sudo apt install screen
see: https://linuxize.com/post/how-to-use-linux-screen/

Screen or GNU Screen is a terminal multiplexer. In other words, it means that you can start a screen session and then open any number of windows (virtual terminals) inside that session. Processes running in Screen will continue to run when their window is not visible even if you get disconnected.
```
screen          :Start a screen session.
screen -r       :Resume a screen session.
screen -list    :Show your current screen sessions.
CTRL-A   :Activate commands for screen.
CTRL-A c :Create a new instance of terminal.
CTRL-A n :Go to the next instance of terminal.
CTRL-A p  :  Go to the previous instance of terminal.
CTRL-A " :Show current instances of terminals.
CTRL-A A :Rename the current instance of terminal.
```

# File Permissions
```
chmod 775 file                  : Change mode of file to 775
chmod -R 600 folder             : Recursively chmod folder to 600
chown                           :Change file owner to user and
user :group file                :group to group
```

# tar
```
tar cf file1.tar dir                     : will comprese the dir folder and name it file.tar
tar xf file.tar                          : extract tar file  'file.tar' 
tar czf file.tar.gz files                :create a tar with Gzip compression
tar xzf file.tar.gz                      :extract a tar using Gzip 
tar cjf file.tar.bz2                     :create a tar with Bzip2 compression
tar xjf file.tar.bz2                     :extract a tar using Bzip2
gzip file                                :compresses fle and renames it to fle.gz
gzip -d file.gz                          :decompresses fle.gz back to fle
```


<br>

# Network
sudo apt install net-tools
sudo apt install whois
<br>

```
1. ping host
example: ping 8.8.8.8                   : ping to google
2. ifconfig                             : network configurations
3. whois domain                         :the whois command line utility is a WHOIS client for communicating with the WHOIS server 
example: whois 216.58.206.46
4. dig domain                           :The dig command in Linux is used to gather DNS information. It stands for Domain Information Groper, and it collects data about Domain Name Servers. The dig command is helpful for troubleshooting DNS problems, but is also used to display DNS information.
example: dig google
5. dig -x host                          : reverse lookup host. The dig command with the -x option to do a reverse DNS lookup. A reverse DNS lookup means you want to look up the domain and host name of an IP address.

6. wget file                            : GNU Wget is a command-line utility for downloading files from the web. With Wget, you can download files using HTTP, HTTPS, and FTP protocols.Wget provides a number of options allowing you to download multiple files, resume downloads, limit the bandwidth, recursive downloads, download in the background, mirror a website, and much more.

example: wget http://releases.ubuntu.com/18.04/ubuntu-18.04-live-server-amd64.iso

7. wget -c file                         : continue download


```

#
