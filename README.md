
EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL
DATE: 28-05-2023
# AIM :
To write a python program to perform sliding window protocol
ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program
CLIENT PROGRAM :
## Developed : VISMAYA.S
## Reg no : 212221230125
# CLIENT PROGRAM : 
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send:"))
l=list(range(size))
s=int(input("Enter Window Size:"))
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
# SERVER PROGRAM :
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
	print(s.recv(1024).decode())
	s.send("acknowledgement recieved from the server".encode())
SERVER OUTPUT :
output
```
# CLIENT OUTPUT :
![CO](https://github.com/VismayaNair/EX-2/assets/93427210/0fe3e2ae-1bfa-4d1b-84f0-bcedb139fd08)

# SERVER OUTPUT :
![SO](https://github.com/VismayaNair/EX-2/assets/93427210/b779e4f0-34af-46bc-93f9-70b5f9c3e532)

# RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.
