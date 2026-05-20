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
## Server
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))

s.listen(5)
print("Server waiting...")

c, addr = s.accept()
print("Connected to", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    if ClientMessage.lower() == "exit":
        break

    print("Client >", ClientMessage)

    msg = input("Server > ")
    c.send(msg.encode())

c.close()
s.close()
```
## Client
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    if msg.lower() == "exit":
        break

    s.send(msg.encode())

    reply = s.recv(1024).decode()
    print("Server >", reply)

s.close()

```
## OUPUT
<img width="1920" height="1080" alt="Screenshot 2026-05-20 085029" src="https://github.com/user-attachments/assets/354e7132-36cb-4564-97de-eb6ef75d6e2f" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
