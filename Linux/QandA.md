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

https://sadservers.com/newserver/taipei

- Port Knocking (Single Knock) https://www.twingate.com/blog/glossary/port%20knocking
- Unlock access to port 80 by sending traffic to a hidden port.

Steps:
- `ss -lntp`          # Check listening ports
- `nmap -p- localhost` # Find all open ports
- `curl localhost:<port>`  # Test suspicious ports (sends TCP SYN)
- `curl localhost`    # Check if port 80 unlocked

```bash
TCP SYN → Hidden Port
        ↓
Firewall Rule Changes
        ↓
Port 80 Opens
```

### Question 4

https://sadservers.com/newserver/lhasa

awk command resources : https://www.geeksforgeeks.org/linux-unix/awk-command-unixlinux-examples/

- `awk ' { sum += $2 } END { avg=sum/NR ; print "Average: " avg } ' scores.txt`


### Question 5

https://sadservers.com/newserver/bucharest

```bash
sudo vi /etc/postgresql/13/main/pg_hba.conf

add this to allow connection:

host   app1    app1user        all     trust
```

- `sudo systemctl restart postgresql`
- `PGPASSWORD=app1user psql -h 127.0.0.1 -d app1 -U app1user -c '\q'`

### Question 6

https://sadservers.com/newserver/bata

- `grep -ir "secret:" ../../proc/sys`
