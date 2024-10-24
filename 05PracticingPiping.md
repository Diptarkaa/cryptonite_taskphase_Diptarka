# 1. Redirecting Output

`hacker@dojo:~$ echo hi > asdf
This will redirect the output of echo hi (which will be hi) to the file asdf. You can then use a program such as cat to output 
this file:
hacker@dojo:~$ cat asdf
hi`

echo  PWN > COLLEGE

# 2. Redirecting more output

# 3. Appending Output

`You can redirect input in append mode using >> instead of >`

 /challenge/run >> /home/hacker/the-flag
 cat /home/hacker/the-flag

 # 4. Redirecting Errors

 `FD 0: Standard Input
FD 1: Standard Output
FD 2: Standard Error
hacker@dojo:~$ some_command > output.log 2> errors.log
That command will redirect output to output.log and errors to errors.log.`

# 5. Redirecting input

echo COLLEGE > PWN
/challenge/run < PWN

# 6. Grepping Stored Results

/challenge/run >  /tmp/data.txt
grep pwn /tmp/data.txt

# 7. Grepping Live Output

`Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the 
command to the right of the pipe. For example:
hacker@dojo:~$ echo no-no | grep yes
hacker@dojo:~$ echo yes-yes | grep yes
yes-yes`

/challenge/run | grep pwn

# 8. Grepping errors

`The shell has a >& operator, which redirects a file descriptor to another file descriptor. This means that we can have a 
two-step process to grep through errors: first, we redirect standard error to standard output (2>& 1) and then pipe the 
now-combined stderr and stdout as normal (|)`

 /challenge/run 2>&1  flag | grep pwn

 # 9. Duplicating piped data with tee

 `The tee command duplicates data flowing through your pipes to any number  of files provided on the command line`
 
 `The two outputs of tee are : first, stdout, and second, a redirect to a file. The stdout gets piped further into the next 
 command. cat ing the file where tee redirected the output of the previous command to gives us the instructions needed to run 
 the final command to get the flag.`
 

 /challenge/pwn | tee output | /challenge/college
 cat output
 /challenge/pwn --secret wUJ_jbFv| tee output | /challenge/college

# 10. Writing to multiple programs

 `hacker@dojo:~$ echo HACK | rev
KCAH
hacker@dojo:~$ echo HACK | tee >(rev)
HACK
KCAH`

`Above, the following sequence of events took place:
bash started up the rev command, hooking a named pipe (presumably /dev/fd/63) to rev's standard input
bash started up the tee command, hooking a pipe to its standard input, and replacing the first argument to tee with /dev/fd/63. tee never even saw the argument >(rev); the shell substituted it before launching tee
bash used the echo builtin to print HACK into tee's standard input
tee read HACK, wrote it to standard output, and then wrote it to /dev/fd/63 (which is connected to rev's stdin)
rev read HACK from its standard input, reversed it, and wrote KCAH to standard output`

 /challenge/hack | tee >(/challenge/the) | /challenge/planet

 # 11. Split-piping stderr and stdout

/challenge/hack 2> >(/challenge/the) | /challenge/planet
