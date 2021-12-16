Section 1.2: File Management Commands
Linux uses some conventions for present and parent directories. This can be a little confusing for beginners.
Whenever you are in a terminal in Linux, you will be in what is called the current working directory. Often your
command prompt will display either the full working directory, or just the last part of that directory. Your prompt
could look like one of the following:
user@host ~/somedir $
user@host somedir $
user@host /home/user/somedir $
which says that your current working directory is /home/user/somedir.
GoalKicker.com – Linux® Notes for Professionals 4
In Linux .. represents the parent directory and . represents the current directory.
Therefore, if the current directory is /home/user/somedir, then cd ../somedir will not change the working
directory.
The table below lists some of the most used file management commands
Directory navigation
Command Utility
pwd Get the full path of the current working directory.
cd - Navigate to the last directory you were working in.
cd ~ or just cd Navigate to the current user's home directory.
cd .. Go to the parent directory of current directory (mind the space between cd and ..)
Listing files inside a directory
Command Utility
ls -l List the files and directories in the current directory in long (table) format (It is recommended to
use -l with ls for better readability).
ls -ld dir-name List information about the directory dir-name instead of its contents.
ls -a List all the files including the hidden ones (File names starting with a . are hidden files in Linux).
ls -F Appends a symbol at the end of a file name to indicate its type (* means executable, / means
directory, @ means symbolic link, = means socket, | means named pipe, > means door).
ls -lt List the files sorted by last modified time with most recently modified files showing at the top
(remember -l option provides the long format which has better readability).
ls -lh List the file sizes in human readable format.
ls -lR Shows all subdirectories recursively.
tree Will generate a tree representation of the file system starting from the current directory.
File/directory create, copy and remove
Command Utility
cp -p source destination
Will copy the file from source to destination. -p stands for preservation. It
preserves the original attributes of file while copying like file owner, timestamp,
group, permissions etc.
cp -R source_dir
destination_dir Will copy source directory to specified destination recursively.
mv file1 file2 In Linux there is no rename command as such. Hence mv moves/renames the
file1 to file2.
rm -i filename
Asks you before every file removal for confirmation. IF YOU ARE A NEW USER
TO LINUX COMMAND LINE, YOU SHOULD ALWAYS USE rm -i. You can specify
multiple files.
rm -R dir-name Will remove the directory dir-name recursively.
rm -rf dir-name
Will remove the directory dir recursively, ignoring non-existent files and will
never prompt for anything. BE CAREFUL USING THIS COMMAND! You can
specify multiple directories.
rmdir dir-name Will remove the directory dir-name, if it's empty. This command can only remove
empty directories.
mkdir dir-name Create a directory dir-name.
mkdir -p dir-name/dir-name Create a directory hierarchy. Create parent directories as needed, if they don't
exist. You can specify multiple directories.
touch filename Create a file filename, if it doesn't exist, otherwise change the timestamp of the
file to current time.
File/directory permissions and groups
Command Utility
GoalKicker.com – Linux® Notes for Professionals 5
chmod <specification> filename Change the file permissions. Specifications = u user, g group, o other, + add
permission, - remove, r read, w write,x execute.
chmod -R <specification> dirname
Change the permissions of a directory recursively. To change permission of
a directory and everything within that directory, use this command.
chmod go=+r myfile Add read permission for the owner and the group.
chmod a +rwx myfile Allow all users to read, write or execute myfile.
chmod go -r myfile Remove read permission from the group and others.
chown owner1 filename Change ownership of a file to user owner1.
chgrp grp_owner filename Change primary group ownership of file filename to group grp_owner.
chgrp -R grp_owner dir-name
Change primary group ownership of directory dir-name to group grp_owner
recursively. To change group ownership of a directory and everything within
that directory, use this command.
Section 1.3: Hello World
Type the following code into your terminal, then press Enter :
echo "Hello World"
This will produce the following output:
Hello World
Section 1.4: Basic Linux Utilities
Linux has a command for almost any tasks and most of them are intuitive and easily interpreted.
Getting Help in Linux
Command Usability
man <name> Read the manual page of <name>.
man <section> <name> Read the manual page of <name>, related to the given section.
man -k <editor> Output all the software whose man pages contain <editor> keyword.
man -K <keyword> Outputs all man pages containing <keyword> within them.
apropos <editor>
Output all the applications whose one line description matches the word editor.
When not able to recall the name of the application, use this command.
help In Bash shell, this will display the list of all available bash commands.
help <name> In Bash shell, this will display the info about the <name> bash command.
info <name> View all the information about <name>.
dpkg -l Output a list of all installed packages on a Debian-based system.
dpkg -L packageName Will list out the files installed and path details for a given package on Debian.
dpkg -l | grep -i <edit> Return all .deb installed packages with <edit> irrespective of cases.
less /var/lib/dpkg/available Return descriptions of all available packages.
whatis vim List a one-line description of vim.
<command-name> --help Display usage information about the <tool-name>. Sometimes command -h also
works, but not for all commands.
User identification and who is who in Linux world
Command Usability
hostname Display hostname of the system.
GoalKicker.com – Linux® Notes for Professionals 6
hostname -f Displays Fully Qualified Domain Name (FQDN) of the system.
passwd Change password of current user.
whoami Username of the users logged in at the terminal.
who List of all the users currently logged in as a user.
w
Display current system status, time, duration, list of users currently logged in on system and other
user information.
last Who recently used the system.
last root When was the last time root logged in as user.
lastb Shows all bad login attempts into the system.
chmod Changing permissions - read,write,execute of a file or directory.
Process related information
Command Usability
top List all processes sorted by their current system resource usage. Displays a continually updated
display of processes (By default 3 seconds). Use q key to exit top.
ps List processes currently running on current shell session
ps -u root List all of the processes and commands root is running
ps aux List all the processes by all users on the current system
Section 1.5: Searching for files by patterns in name/contents
A common and task of someone using the Linux Command Line (shell) is to search for files/directories with a
certain name or containing certain text. There are 2 commands you should familiarise yourself with in order to
accomplish this:
Find files by name
find /var/www -name '*.css'
This will print out the full path/filename to all files under /var/www that end in .css. Example output:
/var/www/html/text-cursor.css
/var/www/html/style.css
For more info:
man find
Find files containing text
grep font /var/www/html/style.css
This will print all lines containing the pattern font in the specified file. Example output:
font-weight: bold;
font-family: monospace;
Another example:
grep font /var/www/html/
GoalKicker.com – Linux® Notes for Professionals 7
This doesn't work as you'd hoped. You get:
grep: /var/www/html/: Is a directory
You need to grep recursively to make it work, using the -R option:
grep -R font /var/www/html/
Hey nice! Check out the output of this one:
/var/www/html/admin/index.php: echo '<font color=red><b>Error: no dice</b></font><br/>';
/var/www/html/admin/index.php: echo '<font color=red><b>Error: try again</b></font><br/>';
/var/www/html/style.css: font-weight: bold;
/var/www/html/style.css: font-family: monospace;
Notice that when grep is matching multiple files, it prefixes the matched lines with the filenames. You can use the -
h option to get rid of that, if you want.
For more info:
man grep
Section 1.6: File Manipulation
Files and directories (another name for folders) are at the heart of Linux, so being able to create, view, move, and
delete them from the command line is very important and quite powerful. These file manipulation commands allow
you to perform the same tasks that a graphical file explorer would perform.
Create an empty text file called myFile:
touch myFile
Rename myFile to myFirstFile:
mv myFile myFirstFile
View the contents of a file:
cat myFirstFile
View the content of a file with pager (one screenful at a time):
less myFirstFile
View the first several lines of a file:
head myFirstFile
View the last several lines of a file:
tail myFirstFile
Edit a file:
GoalKicker.com – Linux® Notes for Professionals 8
vi myFirstFile
See what files are in your current working directory:
ls
Create an empty directory called myFirstDirectory:
mkdir myFirstDirectory
Create multi path directory: (creates two directories, src and myFirstDirectory)
mkdir -p src/myFirstDirectory
Move the file into the directory:
mv myFirstFile myFirstDirectory/
You can also rename the file:
user@linux-computer:~$ mv myFirstFile secondFileName
Change the current working directory to myFirstDirectory:
cd myFirstDirectory
Delete a file:
rm myFirstFile
Move into the parent directory (which is represented as ..):
cd ..
Delete an empty directory:
rmdir myFirstDirectory
Delete a non-empty directory (i.e. contains files and/or other directories):
rm -rf myFirstDirectory
Make note that when deleting directories, that you delete ./ not / that will wipe your whole filesystem