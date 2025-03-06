# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
Server code


# echo-server.py


```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
# echo-client.py


```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Sonu S-212223220107(05-03-2025)")
    data = s.recv(1024)


print(f"Received {data!r}")
```

## OUTPUT:
![Screenshot 2025-03-05 234013](https://github.com/user-attachments/assets/47a2a002-b0d3-4750-bd7c-d77ea0126a87)

![Screenshot 2025-03-05 233529](https://github.com/user-attachments/assets/ac0f22ed-2e51-48b0-9674-dcf75a3ee8d2)


## RESULT:
The program is executed successfully
