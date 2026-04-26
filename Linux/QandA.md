# EASY
### Question 1 

_https://sadservers.com/scenario/saint-john_

- `lsof | grep bad.log` -> find which program is writing to the log file
- `find ./ -name badlog.py`  -> to find the program and delete it
- `ps aux | grep badlog.py` -> to find pid of already running process and kill it using kill <PID>