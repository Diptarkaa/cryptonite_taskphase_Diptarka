# 1. Becoming root with su

`Because it has the SUID bit set, su runs as root. Running as root, it can start a root shell! Of course, su is discerning: 
before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password:`

su
hack-the-planet
cat /flag

# 2. Other users with su

`With no arguments, su will start a root shell (after authenticating with root's password). However, you can also give a 
username as an argument to switch to that user instead of root.`

su zardus
dont-hack-me
/challenge/run

# 3. Cracking Passwords

`A value of * or ! functionally means that password login for the account is disabled, a blank field means that there is no 
password 
John the Ripper can be used to crack the password`

john /challenge/shadow-leak
su zardus
aardvark
/challenge/run

# 4. Using sudo

`Unlike su, which defaults to launching a shell as a specified user, sudo defaults to running a command as root:`

sudo cat /flag
