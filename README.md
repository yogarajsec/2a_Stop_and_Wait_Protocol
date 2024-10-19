# 2a_Stop_and_Wait_Protocol
## Name:Yogaraj.S
## Reg no: 212223040248
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True :
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement received".encode())

```
## OUTPUT:
![Screenshot 2024-10-19 133838](https://github.com/user-attachments/assets/51055cc2-bc02-44b1-af03-58b3de5f95d9)
![Screenshot 2024-10-19 133903](https://github.com/user-attachments/assets/130af2f9-8ad5-4698-b460-9b31e2c56b1b)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
