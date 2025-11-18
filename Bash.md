## 🔥 1. File & Directory Operations (Must Know)
- ls -l            # list with details
- cd /path         # change directory
- mkdir folder     # create folder
- touch file.txt   # create file
- rm file.txt      # remove file
- rm -rf folder/   # delete folder recursively
- cp src dest      # copy file/folder
- mv old new       # move/rename

## 🔥 2. Viewing & Searching Logs
- cat file.log                      # view whole file
- tail -n 50 app.log                # last 50 lines
- tail -f app.log                   # live logs
- grep "ERROR" app.log              # search for string
- grep -i "error" app.log           # case-insensitive
- grep -R "keyword" /var/log/       # recursive search
- awk '{print $1, $5}' file.txt     # column extraction
- sed 's/old/new/g' file.txt        # find & replace

## 🔥 3. Process & System Monitoring
- top                # live system processes
- htop               # better version of top
- ps aux             # all processes
- kill -9 PID        # force kill process
- df -h              # disk usage
- du -sh folder/     # folder size
- free -m            # memory usage
- uptime             # system load

## 🔥 4. Networking Commands
- ifconfig            # network config
- ip a                # show IPs
- ping google.com     # connectivity test
- curl URL            # API call or download
- curl -I URL         # get headers only
- netstat -tulnp      # listening ports
- telnet host port    # test connectivity

## 🔥 5. Automation Basics (Very Likely in Interview)
---
- For Loops
    for i in {1..5}; do
      echo "Number $i"
    done

- While Loop
    while true; do
      echo "running..."
      sleep 10
    done

- If Condition
    if [ -f /tmp/test.txt ]; then
      echo "File exists"
    else
      echo "File missing"
    fi

- Functions
    myfunc() {
      echo "Hello $1"
    }
    
    myfunc World

---
## 🔥 6. API Calls with cURL (VERY IMPORTANT)
- curl -X GET "https://api.example.com/data"
- curl -X POST -d '{"name":"prachi"}' -H "Content-Type: application/json" https://api.example.com/add
- Used often in CI/CD automation.
