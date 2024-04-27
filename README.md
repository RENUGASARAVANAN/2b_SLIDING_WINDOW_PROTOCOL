# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

# Program:
 DEVELOPED BY:S.RENUGA
 REG NO:212222230118

 # Client:
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

# Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
# Output:
# Client:
![Screenshot 2024-04-16 211237](https://github.com/RENUGASARAVANAN/ChatStudy/assets/119292258/38ccd9aa-e24c-4f88-a70d-7cb8230b3ce9)

# Server:
![Screenshot 2024-04-16 211255](https://github.com/RENUGASARAVANAN/ChatStudy/assets/119292258/b83c5fa1-a1a1-4266-b346-8d7a0750b33e)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
