# 2a_Stop_and_Wait_Protocol
## NAME: Vishal S
## REGISTER NUMBER: 212223110063

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
## Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
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
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
![Screenshot 2024-04-05 103529](https://github.com/vishal23000591/2a_Stop_and_Wait_Protocol/assets/147139719/d173022c-6bf1-435f-8ef0-36792ffd8a55)
![Screenshot 2024-04-05 103551](https://github.com/vishal23000591/2a_Stop_and_Wait_Protocol/assets/147139719/f8c00b86-96eb-4a58-9164-b1fbb5514181)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
