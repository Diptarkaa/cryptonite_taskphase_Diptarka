#1. The Root

/pwn
takes us to the pwn directory. / means that it is in the root directory

#2. Program and asolute paths

/challenge/run

#3. Position by thy self

cd /challenge
ls
./run

`It showed:
Incorrect...
You are not currently in the /var directory.`

cd /var
/challenge/run

#4. Position elsewhere

cd /challenge
./run

`It showed:
Incorrect...
You are not currently in the /proc/215 directory.`

cd /proc/215
/challenge/run

#5. Position yet elsewhere

cd /challenge
./run

`It showed:
Incorrect...
You are not currently in the /usr/share/build-essential directory.`

cd /usr/share/build-essential
/challenge/run

#6. implicit relative paths, from /

cd /
challenge/run

#7. explicit relative paths, from /

cd /
./challenge/run

#8. implicit relative path

cd /challenge
./run

#9. home sweet home
