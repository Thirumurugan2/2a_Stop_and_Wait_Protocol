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
# Client:
```
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
```
# Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recieved".encode())
```
## OUTPUT:
# Client:

![310182962-a39d0847-f15e-463f-9356-00c0c40ca10c](https://github.com/Thirumurugan2/2a_Stop_and_Wait_Protocol/assets/162677168/e80facc5-0b90-444d-814b-50f3c6ea72d4)

# Server:


![310183074-39f6cffa-fa72-4ef0-b26f-09f44af81c9b](https://github.com/Thirumurugan2/2a_Stop_and_Wait_Protocol/assets/162677168/fdd3df22-8b1b-4a94-98fe-824c15d22236)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
