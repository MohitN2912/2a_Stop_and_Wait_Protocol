# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Client Side:

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

Server Side:

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())
```

 
## OUTPUT

**Client side**
<img width="917" height="261" alt="Screenshot 2026-05-11 232542" src="https://github.com/user-attachments/assets/eb086821-db1d-4076-a439-eab40a65f0c8" />

**Server side**
<img width="893" height="163" alt="Screenshot 2026-05-11 232550" src="https://github.com/user-attachments/assets/f7d807b6-dc6a-40a2-b5c7-5e4c09c0f226" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
