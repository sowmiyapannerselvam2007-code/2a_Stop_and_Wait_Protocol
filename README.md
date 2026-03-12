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
client.py:
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
```

server.py:
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived from the server".encode())
    
```
## OUTPUT
<img width="703" height="188" alt="Screenshot 2026-03-12 112007" src="https://github.com/user-attachments/assets/dbed0a56-843e-48f9-88f7-0a1d52a578d5" />
<img width="721" height="198" alt="Screenshot 2026-03-12 111816" src="https://github.com/user-attachments/assets/ad7aee3b-fc3e-4893-84f7-aadc510ecc4c" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
