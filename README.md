# Room Temperatue Controlling AI

## Creating a fully functional AI program for room temperature control requires significant development and integration efforts. 
## However, I can provide you with a simplified example of how you can create a basic AI program for room temperature control using Python. 
## Keep in mind that this is a simplified version and may not include all the advanced features mentioned earlier. 
### REG NO:
``` py
S.NO DATE NAME OF THE PROGRAM PG.NO MARKS SIGN
1a Stop and Wait Protocol
1b Sliding window Protocol
2
Study of socket programming with
client server model
3a Simulating ARP
3b Simulating RARP
4a Simulating PING command
4b Simulating TRACEROUTE
5
Application using TCP Sockets
Creation for Echo client and echoserver
6 Application using TCP Sockets
Creation for Chat
7 Application using TCP Sockets
Creation for File Transfer
8
Study of Network simulator (NS) and
Simulation of Congestion Control
Algorithms using NS
9
Case study of Routing Algorithms
10
REG NO:
IMPLEMENTATION OF STOP AND WAIT PROTOCOL
EXP: 1(a)
DATE:
AIM:
To write a python program to perform stop and wait protocol
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:
CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
REG NO:
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
REG NO:
IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
EXP: 1(b)
DATE:
AIM:
To write a python program to perform sliding window protocol
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
PROGRAM:
CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
REG NO:
STUDY OF SOCKET PROGRAMMING AND CLIENT – SERVER MODE
EXP: 2
DATE:
AIM:
To implement socket programming date and time display from client to
server using TCPSockets
ALGORITHM:
Server:
1. Create a server socket and bind it to port.
2. Listen for new connection and when a connection arrives, accept it.
3. Send server‟s date and time to the client.
4. Read client‟s IP address sent by the client.
5. Display the client details.
6. Repeat steps 2-5 until the server is terminated.
7. Close all streams.
8. Close the server socket.
9. Stop.
Client:
1. Create a client socket and connect it to the server‟s port number.
2. Retrieve its own IP address using built-in function.
3. Send its address to the server.
4. Display the date & time sent by the server.
5. Close the input and output streams.
6. Close the client socket.
7. Stop.
PROGRAM:
CLIENT:
REG NO:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode()) 
 
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, the program to implement socket programming date and time display from client to 
server using TCP Sockets was successfully executed.
REG NO:
WRITE A CODE SIMULATING ARP /RARP PROTOCOLS
EXP: 3(a)
DATE:
AIM:
To write a python program for simulating ARP protocols using TCP.
ALGORITHM:
Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
PROGRAM:
CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode()) 
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
REG NO:
PROGRAM FOR REVERSE ADDRESS RESOLUTION PROTOCOL 
(RARP) USING UDP
EXP: 3(B)
DATE:
AIM:
To write a python program for simulating RARP protocols using UDP
ALGORITHM:
Client
1. Start the program
2. Using datagram sockets UDP function is established.
3. Get the MAC address to be converted into IP address.
4. Send this MAC address to server.
5. Server returns the IP address to client.
Server
1. Start the program.
2. Server maintains the table in which IP and corresponding MAC addresses are stored.
3. Read the MAC address which is send by the client.
4. Map the IP address with its MAC address and return the IP address to client.
PROGRAM:
CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode()) 
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
REG NO:
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, python program for simulating RARP protocols using UDP was successfully executed.
REG NO:
WRITE A CODE SIMULATING PING COMMAND
EXP: 4(a)
DATE:
AIM:
To write the python program for simulating ping command.
ALGORITHM:
Step 1: start the program.
Step 2: Include necessary package in java.
Step 3: To create a process object p to implement the ping command.
Step 4: declare one Buffered Reader stream class object.
Step 5: Get the details of the server
 5:1: length of the IP address.
 5:2: time required to get the details.
 5:3: send packets, receive packets and lost packets. 
 5.4: minimum, maximum and average times.
Step 6: print the results. 
Step 7: Stop the program.
PROGRAM:
CLIENT:
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost'8000))
s.listen(5)
c,addr=s.accept()
while True:
 hostname=c.recv(1024).decode()
 try:
 c.send(str(ping(hostname, verbose=False)).encode())
 except KeyError:
 c.send("Not Found".encode())
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter the website you want to ping ")
 s.send(ip.encode())
 print(s.recv(1024).decode())
REG NO:
OUTPUT:
CLIENT:
SERVER:
RESULT:
Thus, the python program for simulating ping command was successfully executed.
REG NO:
WRITE A CODE SIMULATING TRACEROUTE COMMAND
EXP: 4(b)
DATE:
AIM:
To write the python program for simulating Traceroute command
ALGORITHM:
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server, it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
OUTPUT:
RESULT:
Thus, the python program for simulating Traceroute command was successfully executed.


CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
EXP: 5
DATE:
AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server, it will send ACK signal to client otherwise it will
send NACKsignal to client.
6. Stop the program
PROGRAM:
CLIENT:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 msg=input("Client > ")
 s.send(msg.encode())
 print("Server > ",s.recv(1024).decode())
SERVER:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 ClientMessage=c.recv(1024).decode()
 c.send(ClientMessage.encode())
```
 
