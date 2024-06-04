# Testing Latency
### Getting started
- Created this for testing latency and getting notified when my system is showing low latency.

```bash
#!/bin/bash

# THIS SCRIPT IS FOR TESTING PURPOSES.
# USED TO TEST RESPONSE OF A SYSTEM WITH LOW LATENCY. (EX: EMCO)

#\n adds a new line in begging or end of sentence. Option "-e" after echo allows options like \n (newline) or \t (tab) to execute.
echo -e "\n\t================================="
echo -e "\t|                               |"
echo -e "\t| THIS IS A NETWORK TEST SCRIPT |"
echo -e "\t|                               |"
echo -e "\t================================="
echo
sleep 2
read -p "Do you want to test network? (Y/N): " choice
if [[ "$choice" = [Yy] ]]; then
        read -p "Please enter a server ip address to ping: " serv
        echo -e
        sleep 1
        echo -e "Pinging server $serv...\n"
        ping -c 2 "$serv"
        sleep 1
        echo -e " \n"
fi


read -p "Would you like to test latency by adding 200ms? (Y/N): " choice
if [[ "$choice" = [Yy] ]]; then
        read -p "What is your network interface?: (e.g. eth0) " int
        echo -e "\nyou entered $int\n"
        sleep 1
        read -p "Please enter a server ip address to test connection on: " serv
        echo -e "Adding 200ms to $serv with network interface $int\n"
        sleep 1
        sudo tc qdisc add dev $int root netem delay 200ms
        #ping $serv -t
        echo "'sudo tc qdisc del dev $int  root' to stop the 200ms delay "
fi
sleep 1
sleep 3
else
  echo "age not valid"
  echo "18 and up required ;)"
fi
```
