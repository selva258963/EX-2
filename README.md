# IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# EXP: 2

# DATE:15-03-2023

# AIM :
## To write a python program to perform stop and wait protocol


# ALGORITHM :
## 1. . Start the program.
## 2. Get the frame size from the user
## 3. To create the frame based on the user request.
## 4. To send frames to server from the client side.
## 5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
## 6. Stop the program

# CLIENT PROGRAM :
```PYTHON 3 

import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# SERVER PROGRAM :
```PYTHON 3
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())

```


# SERVER OUTPUT :
![240957710-952c947e-3d4c-46ef-acc9-f555432153c9](https://github.com/BalaSathiesh/EX-2/assets/128462891/d2a0b622-539a-47a6-8494-c63bed789e16)


# CLIENT OUTPUT :


![240957673-0e37799e-a40a-4c4f-b83e-32658daa7edd](https://github.com/BalaSathiesh/EX-2/assets/128462891/703c9089-84d6-4bcb-bbaf-e96443b0f75b)

# RESULT :
## Thus, python program to perform stop and wait protocol was successfully executed.






