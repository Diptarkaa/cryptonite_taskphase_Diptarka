# 1. Matching with *

`When it encounters a * character in any argument, the shell will treat it as "wildcard" and try to replace that argument 
with any files that match the pattern.`
cd /ch*
ls
./run

# 2. Matching with ?

`When it encounters a ? character in any argument, the shell will treat it as single-character wildcard. This works like *, 
but only matches one character.`

cd /?ha??enge
./run

# 3. Matching with []

cd /challenge/files
/challenge/run file_[abhs]

# 4. Matching paths with []

`[] is a wildcard for some subset of potential characters, specified within the brackets.`

/challenge/run /challenge/files/file_[absh]

# 5. Mixing globs

cd /challenge/files
/challenge/run  [chedpw]*

# 6. Exclusionary globbing

cd /challenge/files
/challenge/run [!pwn]*
