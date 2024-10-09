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

# 9. An epic Filesystem quest

cd /
ls -a
cat INFO

`Shows the following:
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/sympy/interactive/__pycache__
Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!`

ls  /usr/local/lib/python3.8/dist-packages/sympy/interactive/__pycache__
cat  /usr/local/lib/python3.8/dist-packages/sympy/interactive/__pycache__/ALERT-TRAPPED

`It shows:
Lucky listing!
The next clue is in: /opt/busybox/busybox-1.33.2/include/config/feature/ps/additional
The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.`

cat /usr/local/lib/python3.8/dist-packages/sympy/interactive/__pycache__/ALERT-TRAPPED
cd /opt/busybox/busybox-1.33.2/include/config/feature/ps/additional
ls -a
cat TIP
cd /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX/SizeFourSym 
ls -a
cat .TRACE
cd /usr/share/help/oc/gedit
ls -a
cat INSIGHT
cd /opt/kropr/.git/objects/3a
ls
cat BRIEF
cd /usr/lib/ruby/2.7.0/csv
ls -a
cat REVELATION
cd /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/constants
ls -a
cat SECRET
cd /opt/ghidra/Ghidra/Processors/HCS08/data/languages
cat NOTE-TRAPPED

# 10. Making Directories

mkdir /tmp/pwn
touch /tmp/pwn/college
/challenge/run

`mkdir command is used to create a new directory`

# 11. Finding files

find / -name flag
cat /usr/lib/python3/dist-packages/openid/server/__pycache__/flag

`here we specified / so that it searches for all occurences in the whole file system. If we hadn't specified it, find would have just searched in the current working directory.`

# 12. Linking files

`you want two programs to access the same data, but the programs expect that data to be in two different locations. Luckily, Linux provides a solution to this quandry: links.`

`In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediate yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.`

ln -s /flag ~/not-the-flag
/challenge/catflag

`ln -s actual_file file_referencing_actual_file`
