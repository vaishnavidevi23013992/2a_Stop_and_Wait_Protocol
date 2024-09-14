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

<h2> CLIENT </h2>

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
<h2> SERVER</h2>
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
    ```
    
    
## OUTPUT
<h2>
  CLIENT
</h2>

![image](https://github.com/user-attachments/assets/b1c70c40-85e8-47f1-a71b-4ee13c6d8db9)

<h2> SERVER </h2>

![image](https://github.com/user-attachments/assets/e8e65043-38f3-4da8-b0fc-5998cfd6d6c0)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
