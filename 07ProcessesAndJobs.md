# 1. Listing Processes

ps aux

# 2. Killing Processes

ps -ef | grep /challenge/dont_run
kill 73 
/challenge/run

# 3. Interupting processes

/challenge/run
Ctrl+C

# 4. Suspending Processes

/challenge/run
Ctrl+Z
/challenge/run

# 5. Resuming Processes

/challenge/run
Ctrl+Z
fg

# 6. Backgrounding Processes

`You've resumed processes in the foreground with the fg command. You can also resume processes in the background with the bg command! This will allow the process to keep running, while giving you your shell back to invoke more commands in the meantime.`

`See that T? That means that the process is suspended due to our Ctrl-Z. The S in bash's STAT column means that bash is sleeping while waiting for input. the R in ps's column means that it's actively running, and the + means that it's in the foreground!`

/challenge/run
Ctrl+Z
bg
/challenge/run

# 7. Foregrounding Processes

`fg is used to bring the commands running in background to the foreground`

/challenge/run
Ctrl+Z
bg
fg

# 8. Starting background processes

`Adding an & after a command starts running it in the background, without having to suspend it and then use the bg command.`

/challenge/run &

# 9. Process Exit Codes

/challenge/get-code
echo $?
/challenge/submit-code 15
