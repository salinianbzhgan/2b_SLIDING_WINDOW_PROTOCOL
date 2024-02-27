# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
```
 import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
``` 
## OUPUT
![Screenshot 2024-02-27 044403](https://github.com/salinianbzhgan/2b_SLIDING_WINDOW_PROTOCOL/assets/145742862/b019394b-9b34-45ea-a2c8-7e4cb95df162)

![Screenshot 2024-02-27 044411](https://github.com/salinianbzhgan/2b_SLIDING_WINDOW_PROTOCOL/assets/145742862/5d8c39ba-a238-4eb5-b385-d67cb1f52a83)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
