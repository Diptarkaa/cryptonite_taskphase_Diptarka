`hacker@dojo:~$ mkdir pwn_directory
hacker@dojo:~$ touch college_file
hacker@dojo:~$ ls -l
total 4
-rw-r--r-- 1 hacker hacker    0 May 22 13:42 college_file
drwxr-xr-x 2 hacker hacker 4096 May 22 13:42 pwn_directory
hacker@dojo:~$`

`The File Type
The first character of each line represents the file type. In pwn_directory's case, the d indicates that it's a directory, and 
in college_file's case, the - represents that it's a normal file. There are other types as well, and you will encounter some of 
them later in your pwn.college journey.`

`The Permissions
The next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting the 
permissions that the user who owns the file (termed the "owner") has to the file, 3 characters denoting the permissions that 
the group that owns the file (termed the "group") has to the file, and 3 characters denoting the permissions that all other 
access (e.g., by other users and other groups) has to the file. We will learn all about these later in the module.`

# 1. Changing File Ownership

`Interestingly, we can change the ownership of files! This is done via the chown (change owner) command:
chown [username] [file]
Typically, chown can only be invoked by the root user.`

chown hacker /flag
cat /flag

# 2. Groups and Files

`group ownership can be changed with the chgrp (change group) command!`

chgrp hacker /flag
cat /flag

# 3. Fun with Group names

`You can check what groups you are part of with the id command:`

id
chgrp grp15084 /flag
cat /flag

# 4. Changing Permissions

` r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using cd)`
`- - nothing `

`Like ownership, file permissions can also be changed. This is done with the chmod (change mode) command.`

`You can specify the MODE in two ways: as a modification of the existing permissions mode, or as a completely new mode to overwrite the old one.
In this level, we will cover the former: modifying an existing mode. chmod allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute. For example, to add read access for the owning user, you would specify a mode of u+r. write and execute access for the group and the other (or all the modes) are specified the same way. More examples:
u+r, as above, adds read access to the user's permissions
g+wx adds write and execute access to the group's permissions
o-w removes write access for other users
a-rwx removes all permissions for the user, group, and world`

chmod ugo+rwx /flag
cat /flag

# 5. Executable files.

chmod ugo+x /challenge/run
/challenge/run

# 6. Permission Tweaking Practice

chmod ugo+rw /challenge/pwn

`similarly we had to change the permissions 8 times as asked by the terminal`

chmod ugo+rw /flag
cat /flag

# 7. Permissions Setting Practice

`chmod can also simply set permissions altogether, overwriting the old ones. This is done by using = instead of - or +.`

chmod u=wx,go=x /challenge/pwn
`similarly we had to change the permissions 8 times as asked by the terminal`

chmod a=rwx /flag
cat /flag

# 8. The SUID Bit

`There are many cases in which non-root users need elevated access to do certain system tasks. The system admin can't be there to give them the password every time a user wanted to do a task that only root/sudoers can do. The "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.`

`The s part in place of the executable bit means that the program is executable with SUID. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user).`

chmod u+s /challenge/getroot
/challenge/getroot
cat /flag

