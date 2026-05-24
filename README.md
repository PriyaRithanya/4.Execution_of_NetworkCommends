# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program
```
client side:

import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
  ip=input("Enter the website you want to ping ")
  s.send(ip.encode())
  print(s.recv(1024).decode())

server side:

import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
while True:
  hostname=c.recv(1024).decode()
  try:
    c.send(str(ping(hostname, verbose=False)).encode())
  except KeyError:
    c.send("Not Found".encode())
 ```   
## Output
<img width="1465" height="972" alt="Screenshot (173)" src="https://github.com/user-attachments/assets/288ee178-d230-4a6f-8d33-66bbbb0f70e2" />
<img width="1443" height="851" alt="Screenshot (173)" src="https://github.com/user-attachments/assets/877c1494-ea13-4ec9-884c-7ebd45301b2c" />


## Result
Thus Execution of Network commands Performed 
