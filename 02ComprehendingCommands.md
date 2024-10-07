# 1. cat: not the pet, but the command

cat flag

# 2. Catting absolute paths

cat /flag

# 3. More catting practice

`It showed:
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/share/lintian/flag. Go cat it out **without** cding into that 
directory!`

cat /usr/share/lintian/flag

# 4. Grepping for a needle in a haystack

grep pwn.college /challenge/data.txt

# 5. Listing files

ls /challenge
`showed that there is a file named 24923-renamed-run-23141`

cd /challenge
./24923-renamed-run-23141

# 6. Touching files

` touch command is used to create a new file`
touch /tmp/pwn
touch /tmp/college
/challenge/run

# 7. Removing files

`rm command is used to remove a file`
rm delete_me
/challenge/check

# 8. Hidden files

cd /
ls -a
`gave a hidden file named .flag-8867748719146`

cat .flag-8867748719146
