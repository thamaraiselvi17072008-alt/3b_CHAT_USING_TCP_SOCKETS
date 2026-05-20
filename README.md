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
SERVER
```
import socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))
server_socket.listen(1)
print("Waiting for client connection...")
client_socket, addr = server_socket.accept()
print("Connected to:", addr)
while True:
 client_message = client_socket.recv(1024).decode()
 print("Client:", client_message)
 if client_message.lower() == "bye":
  break
 message = input("Server: ")
 client_socket.send(message.encode())
 if message.lower() == "bye":
  break
client_socket.close()
server_socket.close()
```
CLIENT
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
client_socket.connect((host, port))
print("Connected to server")
while True:
 message = input("Client: ")
 client_socket.send(message.encode())
 if message.lower() == "bye":
  break
 server_message = client_socket.recv(1024).decode()
 print("Server:", server_message)
 if server_message.lower() == "bye":
  break
client_socket.close()
```
## OUPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2ecdc8a0-c30c-4c73-9980-59ce4eee286c" />

## RESULT

Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
