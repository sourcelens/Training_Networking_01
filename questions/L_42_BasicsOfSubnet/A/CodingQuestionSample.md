
---
In the below code what line     
```
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
does?

```
    # https://realpython.com/python-sockets/
    
    import socket
    import threading
    
    def ThreadfuncForClient( conn, addr ):
        print(f"Connected by {addr}")
        data = conn.recv(1024)
        conn.sendall(data + b" from server")
        conn.close()
    
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.bind(("127.0.0.1", 65432))
    s.listen()
    
    while True:
        conn, addr = s.accept()
        thread_for_client = threading.Thread(target=ThreadfuncForClient, args=(conn, addr))
        thread_for_client.start()

```

1. Create a socket
2. Assign memory to variable s
3. Bind ipaddress to socket
4. Connect to client

**Answer:** 1 Create a socket.

**Reason:**
The line 
```
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
Creates a socket object.

---
