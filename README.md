# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# NAME: DEVA DHARSHINI I

# REGISTER NO: 212223240026
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
CLIENT
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))
```
SERVER
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## OUPUT
CLIENT
![Screenshot 2024-05-07 084304](https://github.com/deesk13/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/150927063/8e12ef30-b330-46d6-a024-40af188711b0)
SERVER
![Screenshot 2024-05-07 084326](https://github.com/deesk13/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/150927063/d23b1011-d18a-4adf-bca7-fd4f4ff47315)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
