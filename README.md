# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
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

server:

```

import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Echo Server waiting for client...")

c, addr = s.accept()
print("Client connected:", addr)

while True:
    data = c.recv(1024).decode()

    if not data:
        break

    print("Received from client:", data)

    c.send(data.encode())

c.close()
s.close()


```

client:


```

import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to Echo Server")

while True:
    msg = input("Enter a message: ")

    if msg.lower() == "exit":
        break

    s.send(msg.encode())

    data = s.recv(1024).decode()

    print("Echo from server:", data)

s.close()

```



## OUPUT


server:

<img width="596" height="456" alt="Screenshot 2026-11-26 140943" src="https://github.com/user-attachments/assets/8486ba9e-fe1b-45de-a374-3057ea6911b6" />


client:


<img width="558" height="405" alt="Screenshot 2026-11-26 140935" src="https://github.com/user-attachments/assets/fc4ee3b2-9ba2-4817-8005-663e7298e3fa" />



## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
