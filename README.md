# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name:A.LAHARI
## REG NO:212223230111
## AIM:
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:

## CLIENT:
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
## SERVER:
```
import socket    
s=socket.socket()   
s.connect(('localhost',8000))   
while True:    
 print(s.recv(1024).decode())    
 s.send("acknowledgement recived from the server".encode())
 
```
## OUTPUT:

## CLIENT:

![Screenshot 2024-04-12 194831](https://github.com/AnnaLahari/2b_SLIDING_WINDOW_PROTOCOL/assets/149365425/a2873fd9-01c4-453f-b3a6-74d924485b7b)

## SERVER:

![Screenshot 2024-04-12 194853](https://github.com/AnnaLahari/2b_SLIDING_WINDOW_PROTOCOL/assets/149365425/bbe885eb-b40b-496b-92b8-20e4f38b3756)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed
