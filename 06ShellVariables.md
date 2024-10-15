# 1. Printing Variables

echo $FLAG

# 2. Setting Variables

PWN=COLLEGE

# 3. Multi-word variables

PWN="COLLEGE YEAH"

# 4. Exporting Variables

export PWN=COLLEGE
COLLEGE=PWN
/challenge/run

# 5. Printing Exported Variables

env

# 6. Storing Command Output


`to store the output of some command into a variable. Example:
hacker@dojo:~$ FLAG=$(cat /flag)
hacker@dojo:~$ echo "$FLAG"
pwn.college{blahblahblah}`

PWN=`/challenge/run`  
`we could've also written PWN=$(/challenge/run)`
echo "$PWN"

# 7. Reading Input

read -p "INPUT: " PWN
INPUT: COLLEGE

# 8. Reading Files

read PWN <  /challenge/read_me
