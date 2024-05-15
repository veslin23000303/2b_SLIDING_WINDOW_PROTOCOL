# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME:VESLIN ANISH A
## REGISTER NO:212223240175
## AIM:
To implement of sliding window protocal.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter Window Size: "))
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
    s.send("acknowledgement recieved from the server".encode())
```
## OUPUT:
## CLIENT:
![Screenshot 2024-05-15 100243](https://github.com/veslin23000303/2b_SLIDING_WINDOW_PROTOCOL/assets/151148539/84238565-2061-4703-b568-ba966b2a0785)



## SERVER:
![Screenshot 2024-05-15 100252](https://github.com/veslin23000303/2b_SLIDING_WINDOW_PROTOCOL/assets/151148539/7f8c8a93-8e35-4ddd-94f7-7e126c7250a4)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
