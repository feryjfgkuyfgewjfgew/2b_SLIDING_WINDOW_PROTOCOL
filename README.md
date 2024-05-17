
# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME:NARESH.R
## REG NO : NARESH.R
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```
## client
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
## OUPUT
## clint
![image](https://github.com/feryjfgkuyfgewjfgew/2b_SLIDING_WINDOW_PROTOCOL/assets/150319377/33320514-2efb-436e-87bd-6cad544564c4)


## server
![Screenshot 2024-05-17 133916](https://github.com/feryjfgkuyfgewjfgew/2b_SLIDING_WINDOW_PROTOCOL/assets/150319377/a48a1a22-977c-4190-9e2d-d098d8f580d2)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
