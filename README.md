# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## DATE : 20/03/23

## AIM :

To write a python program to perform sliding window protocol

## ALGORITHM :

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program

## PROGRAM :
### Client :
```python 
Developed by : Tejusve Kabeer.F
Register no : 212222100054

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
### Server :
```python
Developed by : Tejusve Kabeer.F
Register no : 212222100054

import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUTPUT :
### clientoutput :
![co](https://github.com/Reebak04/EX-3/assets/118364993/2bfbad6b-6388-4fbc-b255-ab032c6c4c36)

### Serveroutput :
![so](https://github.com/Reebak04/EX-3/assets/118364993/390f2eed-aba8-47d4-a90e-9d543f38e20e)

## RESULT :
Thus, python program to perform sliding window protocol was successfully executed.
