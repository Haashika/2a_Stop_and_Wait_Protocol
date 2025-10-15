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
SERVER PROGRAM:
```
import socket 
s = socket.socket() 
s.bind(('localhost', 8000)) 
s.listen(5) 
c, addr = s.accept() 

while True: 
    i = input("Enter a data: ") 
    c.send(i.encode())       
    print("Type your text")  
    ack = c.recv(1024).decode()  
    if ack: 
        print(ack)          
        continue 
    else: 
        c.close() 
        break
```

  CLIENT PROGRAM:
```
import socket 
s = socket.socket() 
s.connect(('localhost', 8000)) 

while True: 
    print(s.recv(1024).decode())  
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT OUTPUT

<img width="613" height="314" alt="Screenshot 2025-10-15 104201" src="https://github.com/user-attachments/assets/8c0bf797-3e95-452e-9b52-7b21c4f9bad3" />

SERVER OUTPUT

<img width="566" height="256" alt="Screenshot 2025-10-15 104216" src="https://github.com/user-attachments/assets/ccbba400-4b37-44e8-82ac-25c22db45431" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
