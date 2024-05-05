# 5a_Create_Socket_for_HTTP_for_webpage_upload_and_download
# NAME : MOHAMED RIDWAN A
# REG NO : 212223110030
## AIM :
To write a PYTHON program for socket for HTTP for web page upload and download
## Algorithm

1.Start the program.
<BR>
2.Get the frame size from the user
<BR>
3.To create the frame based on the user request.
<BR>
4.To send frames to server from the client side.
<BR>
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
<BR>
6.Stop the program
<BR>
## Program 
```
#Name: Mohamed Anas O.I
#Reg No: 212223110028

import socket

port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)

print("Server listening on port", port)

while True:
    conn, addr = s.accept()
    print("Connected to", addr)
    
    data = conn.recv(1024)
    print('Server received', repr(data))

    filename = 'D:\\CSE-IOT\\Computer Networks\\Projects\\Ex_3c\\sample.txt'
    with open(filename, 'rb') as f:
        l = f.read(1024)
        while l:
            conn.send(l)
            print('Sent', repr(l))
            l = f.read(1024)
    
    print('Done sending')
    conn.send('Thank you for connecting'.encode())
    conn.close()

```
## OUTPUT
![Screenshot 2024-04-29 143857](https://github.com/Anas536/5a_Create_Socket_for_HTTP_for_webpage_upload_and_download/assets/139841834/01769300-f9ce-4776-bcdf-046cd97dc40a)

## Result
Thus the socket for HTTP for web page upload and download created and Executed
