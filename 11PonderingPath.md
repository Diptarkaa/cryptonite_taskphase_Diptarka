# 1. The PATH variable

 PATH=" "
 /challenge/run

 # 2. Setting PATH

PATH=/challenge/more_commands/
/challenge/run

# 3. Adding commands

vim win
cat win
cat /flag
chmod +x win
PATH="$PATH:/home/hacker"
/challenge/run

# 4. Hijacking Commands

PATH=/home/hacker:$PATH
nano rm
cat rm
cat /flag
/challenge/run
