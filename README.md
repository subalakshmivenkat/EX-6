# EX-6 IMPLEMENTATION OF PING COMMAND

## DATE : 

12-04-2023
## AIM :
To write the python program for simulating ping command.

## ALGORITHM :
1: Start the program.
2: Include necessary package in java.
3: To create a process object p to implement the ping command.
4: declare one Buffered Reader stream class object.
5: Get the details of the server
 5:1: length of the IP address.
 5:2: time required to get the details.
 5:3: send packets, receive packets and lost packets.
 5.4: minimum, maximum and average times.
6: Print the results.

## PROGRAM :
## CLIENT :
Developed By : SUBALAKSHMI V
Register Number : 212222040162
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER :
Developed By : SUBALAKSHMI V
Register Number : 212222040162
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
## OUTPUT :
![image](https://github.com/subalakshmivenkat/EX-6/assets/119393477/1362a67b-d930-4da4-b51f-d3fc7ec7e4b1)

## RESULT :
Thus, the python program for simulating ping command was successfully executed.
