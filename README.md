# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### client:
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
### server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### client:
![307858770-273c86af-67d6-4287-86ad-8890dfe9a026](https://github.com/codedbykishore/2b_SLIDING_WINDOW_PROTOCOL/assets/147139122/7c9623da-22cf-441a-9a94-214a2d997a85)



### server:
![307858861-9d95f4ae-1b1d-441d-b6c7-335c4bcb6d0d](https://github.com/codedbykishore/2b_SLIDING_WINDOW_PROTOCOL/assets/147139122/a8470e8f-2a2b-490f-948a-d5c61d46eaac)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
