# EASY
### Question 1 

_https://sadservers.com/scenario/saint-john_

- _lsof | grep bad.log_ -> find which program is writing to the log file
- _find ./ -name badlog.py_  -> to find the program and delete it
- _ps aux | grep badlog.py_ -> to find pid of already running process and kill it using kill <PID>