# EASY
### Question 1 

https://sadservers.com/scenario/saint-john

- `lsof | grep bad.log` -> find which program is writing to the log file
- `find ./ -name badlog.py`  -> to find the program and delete it
- `ps aux | grep badlog.py` -> to find pid of already running process and kill it using kill <PID>


### Question 2

https://sadservers.com/scenario/saskatoon

- `awk '{print $1}' /home/admin/access.log | sort | uniq -c | sort | tail -1 | awk '{print $2}' > /home/admin/highestip.txt`


### Question 3