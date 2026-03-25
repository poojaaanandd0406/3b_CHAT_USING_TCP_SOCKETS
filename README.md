# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
## server.py
```
import socket
s = socket.socket()
s.bind(('127.0.0.1', 8000))
s.listen(5)   
print("Server is listening...")
c, addr = s.accept()
print("Connected with", addr)
while True:
    ClientMessage = c.recv(1024).decode()
    if ClientMessage.lower() == "exit":  
        break
    print("Client :", ClientMessage)
    msg = input("Server : ")
    c.send(msg.encode())   
s.close()
c.close()
```
## client.py
```
import socket
s = socket.socket()
s.connect(('127.0.0.1', 8000))
print("Connected to server. Type 'exit' to quit.")
while True:
    msg = input("Client : ")
    if msg.lower() == "exit":   
        s.send(msg.encode())
        break
    s.send(msg.encode())
    reply = s.recv(1024).decode()
    print("Server :", reply)
s.close()
```
## OUPUT
<img width="1109" height="273" alt="image" src="https://github.com/user-attachments/assets/50340d27-580f-4b13-bc3d-3440c3c53814" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
